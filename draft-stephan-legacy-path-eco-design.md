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

  IVY-WG:
    title: "Network Inventory YANG"
    date: 2023-06-23
    target: "https://datatracker.ietf.org/wg/ivy"

  GREEN-BOF:
    title: "BOF proposal for GREEN WG Creation"
    date: 2024-05-10
    target: "https://github.com/marisolpalmero/GREEN-bof"

  SUST-INS:
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

  POWEFF:
    title: "Power and Energy Efficiency"
    date: 2024-05-07
    target: "https://datatracker.ietf.org/doc/html/draft-opsawg-poweff"
    author:
			- ins: Jan Lindblad
			- ins: Snezana Mitrovic
			- ins: Marisol Palmero
			- ins: Gonzalo Salgueiro

--- abstract

This draft discusses the usage of inventory information for assessing the adaptation of existing devices to eco-design. It is driven by the weight of the manufacturing in the sustainability cost with regard to the power consumption.

--- middle

# Introduction

Many companies in Europe have integrated sustainability improvements into their core business strategies. It is driven by a growing awareness of environmental issues and regulatory requirements like CSRD (Corporate Sustainability Reporting Directive), a regulatory framework proposed by the European Commission to enhance corporate transparency and ensure that companies provide comparable information to assess their sustainability performance.

Sustainability impacts numerous aspects of the life cycle management (LCM) of devices. In this draft we discuss the advantages of leveraging existing devices modularity to introduce eco-designed components in the networks while being able to assess the gains in sustainability.

The rational is the urgent need to start decreasing resource consumption by simply replacing devices components. It can be view as a very basic use case of GREEN-bof {{GREEN-BOF}} approach which enable the comparison  of power consumption of legacy line cards with eco-designed line cards.

# Conventions and Definitions

{::boilerplate bcp14-tagged}

# Network and devices modularity

Networks and theirs devices are modular per design to cope with manufacturing and operationnal obvious constraints. Existing devices are going to be progressively replaced with eco-design products. Both will co-exist in the networks as there is a balance to find between the increase of the live duration of existing devices and their replacement with eco-design devices {{SUST-INS}}.

The same approach applies at the same time to individual devices: legacy devices will include progressively more and more eco-designed hardware components.

Eco Design means that the products include environmental considerations throughout their entire lifecycle to reduce their environmental impact. In France they are based on General Reference Base for Eco-Design in digital services (“RGESN”) at  https://ecoresponsable.numerique.gouv.fr/publications/referentiel-general-ecoconception/.

Eco-design can be summarized as the concepts and current practices related to the integration of environmental aspects into every stage of a product lifecycle. This starts at product design and development [ISO/TR 14062:2002 ]

The upgrade of legacy devices with eco-designed cards can be separate in 2 categories:

 * "Simple" update : The adaptation is simple, a card is 'just' replaced with another one which consumes significally less power by itself when running and which required less ressources during its manufacturing and its deployment.

 * "Complex" update: The replacement of the card requires the adding or the update of software components to enable dynamic power consumption.

# Simple Update

Network operators update their devices components since decades. By consequence, update with eco-designed components can started immediatly as there is no dependency on management solutions. The assessement of environmental and power gains can be done manually from the datasheets of the manufacturer or using an adhoc processing.

In the mid term, in a way to scale the assessement, inventory {{IVY-WG}} requires to distinguish both legacy devices which include eco-designed components and these components inside the device. This must not delay the initial deployment of eco-designed components in legacy devices

# Complex Update

Currently network devices are mostly always-on. The design of their software components do not include dynamic power management.

The update of legacy networks and devices to support dynamic power management is something complex because it impacts the different type of components:

  * hardware component must support variation of power, of bit rate or only being shutdown and restarted
  * firmware component must expose the monitoring and the actionable functions to the software components
  * software component must be updated or added to operate these new capabilities

Legacy hardware component are designed for being rarely stop and re-started. The rythm of start/stop supported by the component must be documented immediatly in the datasheet.

# Gain measurements

On the short term, as promoted by the GREEN-BoF, the assessement at the device level requires datamodels augmentation {{IVY-WG}} to expose these configuration updates and metrics to measure the power consumption {{POWEFF}}.

There is room for hackathon sessions to compare asessment methods.

# Security Considerations

The tracking of LCM information may reveal information of the device usages.

# IANA Considerations

At this step this document has no IANA actions.

--- back

# Acknowledgments
{:numbered="false"}

TODO acknowledge.
