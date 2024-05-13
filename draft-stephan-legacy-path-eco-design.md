---
title: "legacy modularity usage for eco-conception"
abbrev: "legacy modularity and eco-design"
docname: draft-stephan-legacy-path-eco-design-latest

category: info
submissiontype: IETF  # also: "independent", "editorial", "IAB", or "IRTF"
consensus: true
area: OPS
workgroup: WG Working Group
keyword: Sustainability, Ressources

venue:
  group: "Green BoF"
  type: "individual"
  mail: "green-bof@ietf.org"
  arch: "https://mailarchive.ietf.org/arch/browse/green-bof/"
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

  SUSTINS:
    title: "Sustainability Insights"
    date: 2023-10-20
    target: "https://datatracker.ietf.org/doc/draft-almprs-sustainability-insights/"
    author:
			- ins: Per Andersson
			- ins: Jan Lindblad
			- ins: Snezana Mitrovic
			- ins: Marisol Palmero
			- ins: Esther Roure
			- ins: Gonzalo Salgueiro
			- ins: Stephan Emile

--- abstract

This draft discusses the usage of inventory information for assessing the adaptation of existing devices to eco-design. It is driven by the weight of the manufacturing in the sustainability cost with regard to the power consumption.

--- middle

# Introduction

Many companies in Europe have integrated sustainability improvements into their core business strategies. It is driven by a growing awareness of environmental issues and regulatory requirements like CSRD (Corporate Sustainability Reporting Directive), a regulatory framework proposed by the European Commission to enhance corporate transparency and ensure that companies provide comparable information to assess their sustainability performance.

Sustainability impacts numerous aspects of the life cycle management (LCM) of devices. In this draft we discuss the advantages of leveraging existing device modularity to introduce eco-designed components in the networks.

The rational is the urgent need to start decreasing resource consumption by simply replacing device components. It can be view as a very basic use case of GREEN-bof approach to compare the power consumption of legacy line cards with eco-designed line cards.

# Conventions and Definitions

{::boilerplate bcp14-tagged}

# Network and devices modularity

Networks and theirs devices are modular per design to cope with manufacturing and operationnal obvious constraints. Existing devices are going to be progressively replaced with eco-design products. Both will co-exist in the networks as there is a balance to find between the increase of the live duration of existing devices and their replacement with eco-design devices {{SUSTINS}}.

The same approach will apply at the same time to individual devices: legacy devices will include progressively more and more eco-designed components.

These hardware components update can be separate in 2 categories:

 * "Simple" update : The adaptation is simple, a card is 'just' replaced with another one which consume significally less power when running and which required less ressources during its manufacturing and its deployment.

 * "Complex" update: The replacement of the component requires the adding or the update of software components to enable dynamic power consumption.

# Simple Update

## LCM

Eco Design means that the products and services include environmental considerations throughout their entire lifecycle to reduce their environmental impact. In France they are based on General Reference Base for Eco-Design in digital services (“RGESN”) at  https://ecoresponsable.numerique.gouv.fr/publications/referentiel-general-ecoconception/.

Eco-design can be summarized as the concepts and current practices related to the integration of environmental aspects into every stage of a product lifecycle. This starts at product design and development [ISO/TR 14062:2002 ]

The refurbishment of existing devices with eco-designed components is part of LCM. Its assessement at the device level requires some datamodel adaptation to track these configuration updates and metrics to measure the power consumption.

## Impact on datamodels

modularity: info models to describe that, state, what was changed, what was adapted to sustainability, which part is adapted to eco design, on which aspect

Does the datamodel need to say that the device modularity has changed ? An example is the chnage of a power block to a modular power block

Measurement of the gain.

# complex Update

The increase of the live duration of existing devices will require managing the replacement of software and firmware components of the devices:

Currently the design of the software components of networks always-on devices do not include, or very recently include, eco conception. Their softwares have to be prepared as their firmware can be adapted to reduce existing hardware power consumptions, bits rates ...

Firmware:

Currently the design of the firmware of most of devices do not include eco design. Firmware must be adapted to receive components from eco conception. This applies especially to the control of hardware parts recently designed to reduce dynamically their power consumptions, their bits rates or both. This is covered by works like sustainality and poweff drafts..

# Gain measurements

There is room for hackathon sessions to compare testing measurements of the gains in power consumption. this may include the power consumption of the testing solutions

# Security Considerations

The tracking of LCM information may reveal to third parties information of the device usages.

Dynamically controled power may introduce weakeness in networking performance and resiliency.

# IANA Considerations

At this step this document has no IANA actions.

--- back

# Acknowledgments
{:numbered="false"}

TODO acknowledge.
