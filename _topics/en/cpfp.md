---
title: "Child pays for parent (CPFP)"
shortname: cpfp

## Optional.  An entry will be added to the topics index for each alias
aliases:
  - Ancestor feerate mining

## Required.  At least one category to which this topic belongs.  See
## schema for options
categories:
  - Fee Management
  - Mining

## Required.  Use Markdown formatting.  Only one paragraph.  No links allowed.
## Should be less than 500 characters
excerpt: >
  **Child Pays For Parent (CPFP)** is a fee bumping technique where a
  user spends an output from a low-feerate unconfirmed transaction in a
  child transaction with a high feerate in order to encourage miners to
  include both transactions in a block.

## Optional.  Produces a Markdown link with either "[title][]" or
## "[title](link)"
primary_sources:
  - title: Mempool and mining in Bitcoin Core
    link: https://github.com/bitcoin-core/bitcoin-devwiki/wiki/Mempool-and-mining

  - title: "Bitcoin Core #7600: ancestor feerate mining"
    link: https://github.com/bitcoin/bitcoin/pull/7600

## Optional.  Each entry requires "title", "url", and "date".  May also use "feature:
## true" to bold entry
optech_mentions:
  - title: Simplified fee bumping for LN
    url: /en/newsletters/2018/11/27/#simplified-fee-bumping-for-ln

  - title: CPFP carve-out proposed
    url: /en/newsletters/2018/12/04/#cpfp-carve-out

  - title: "LND #3140 adds support for RBF and CPFP fee bumping sweep transactions"
    url: /en/newsletters/2019/06/19/#lnd-3140

  - title: "Refactor preparing for ancestor relay"
    url: /en/newsletters/2019/09/25/#bitcoin-core-16400

  - title: Copay adds support for CPFP fee bumping incoming transactions
    url: /en/newsletters/2020/05/20/#copay-enables-cpfp-for-incoming-transactions

  - title: Challenges of using CPFP fee bumps for LN commitment transactions
    url: /en/newsletters/2021/04/21/#using-anchor-outputs-by-default-in-lnd

  - title: "Bitcoin Core #21359 allows CPFP fee bumping incoming payments"
    url: /en/newsletters/2021/05/19/#bitcoin-core-21359

  - title: Sparrow 1.4.0 adds support for CPFP fee bumping from transaction list
    url: /en/newsletters/2021/05/19/#sparrow-1-4-0-released

  - title: Candidate set block templates may make some CPFP fee bumps more effective
    url: /en/newsletters/2021/06/02/#candidate-set-based-csb-block-template-construction

  - title: Proposal of initial CPFP rules for mempool package acceptance before implementing package relay
    url: /en/newsletters/2021/09/22/#package-mempool-acceptance-and-package-rbf

## Optional.  Same format as "primary_sources" above
see_also:
  - title: CPFP carve-out
    link: topic cpfp carve out
---
Bitcoin consensus rules require that the transaction which creates an
output must appear earlier in the block chain than the transaction
which spends that outputs---including having the parent transaction
appear earlier in the same block than the child transaction if both
are included in the same block.

This means that an unconfirmed transaction with a high feerate can
incentivize miners to mine any of its ancestor transactions that are
also unconfirmed.  Nodes such as Bitcoin Core that implement such
transaction selection policies for their block templates call this
*ancestor feerate mining*.  As long as a moderate percentage of miners
implement ancestor feerate mining, wallets can use CPFP as a fee
bumping technique.

{% include references.md %}
