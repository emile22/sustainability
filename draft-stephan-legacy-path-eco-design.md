---
title: "legacy modularity usage for eco-conception"
abbrev: "legacy modularity and eco-design"
docname: draft-stephan-legacy-path-eco-design-latest

category: info
submissiontype: IETF  # also: "independent", "editorial", "IAB", or "IRTF"
consensus: true
area: OPS
workgroup: WG Working Group
keyword: Sustainability

venue:
  group: "Green BoF"
  type: "individual"
  mail: "e-impact@ietf.org"
  arch: "https://mailarchive.ietf.org/arch/browse/e-impact/"
  github: "emile22/sustainability"
  latest: "https://emile22.github.io/sustainability/draft-stephan-legacy-path-eco-design.html"

v: 3

author:

   name: Emile Stephan
   organization: Orange
   street: 2, avenue Pierre Marzin
   city: Lannion
   code: 22300
   country: France
   email: emile.stephan@gmail.com

normative:
  RFC2119:

informative:
  RFC6241:

--- abstract

This draft discusses the usage of inventory information for adapting parts of existing device to eco-design. It is driven by the weight of the manufacturing in the sustainability and resiliency cost wrt to the power consumption.

--- middle

# Introduction

Many companies in Europe have integrated sustainability improvements into their core business strategies. It is driven by a growing awareness of environmental issues and regulatory requirements like CSRD (Corporate Sustainability Reporting Directive), a regulatory framework proposed by the European Commission to enhance corporate transparency and ensure that companies provide comparable information to assess their sustainability performance.

Sustainability impacts numerous aspects of the life cycle management (LCM) of devices. In this draft we discuss the advantages of leveraging existing device modularity to increase sustainability performance faster.

We first recall different uses cases where the levels of modularity requirements are different (Aka velodrome, shopping center ...). Then we present how sustainability impacts device modularity (eco design power management, circular economy ...) Device modularity is usually per design, finally we identify device modularity aspects to explicitly specified and standardized.

Eco conception of new devices is not discussed in this draft.

# Conventions and Definitions

{::boilerplate bcp14-tagged}

# Existing devices modularity

There is a balance to find between the increase of the live duration of existing devices and their replacement with eco-design devices. In the mean time both are going to be included in sustainability approaches and they will co-exist in the networks. In addition legacy devices will include more and more ecodesigned components.

The increase of the live duration of existing devices will require managing the replacement not only of physical components but of any artifacts of the device:

Hardware: cards and physical blocks (power ...)

Software:

Currently the design of always-on devices software do not include eco design. Their softwares have to be prepared as their firmware can be adapted to reduce existing hardware power consumptions, bits rates ...

Firmware:

Currently the design of the firmware of most of devices do not include eco design. Firmware must be adapted to receive components from eco conception. This applies especially to the control of hardware parts recently designed to reduce dynamically their power consumptions, their bits rates or both. This is covered by works like sustainality and poweff drafts.

In summary: the work on reporting real time power efficiency is started. On the other hand, there are evolutions toward more sustainability which require the reporting of just static information which must be specified.

Examples:

case of PoE

# Existing device modularity and eco design

There are numerous definitions of eco design:

Eco Design means that the products and services include environmental considerations throughout their entire lifecycle to reduce their environmental impact pursuant to Orange defined internal process(es), which are  based on France’s General Reference Base for Eco-Design in digital services (“RGESN”) at  https://ecoresponsable.numerique.gouv.fr/publications/referentiel-general-ecoconception/.

Eco-design can be summarized as the concepts and current practices related to the integration of environmental aspects into every stage of a product lifecycle. This starts at product design and development [ISO/TR 14062:2002 ]

The refurbishment of existing devices with eco designed parts is part of LCM. datamodel pieces are needed to track these configuration updates.

# Security Considerations

The tracking of LCM information may reveal information on the owner of the device


# IANA Considerations

This document has no IANA actions.


--- back

# Acknowledgments
{:numbered="false"}

TODO acknowledge.
