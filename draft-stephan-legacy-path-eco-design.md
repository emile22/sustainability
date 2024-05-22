---
title: "legacy modularity usage for eco-conception"
abbrev: "legacy modularity and eco-design"
docname: draft-stephan-legacy-path-eco-design

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
  latest: "https://emile22.github.io/sustainability/draft-stephan-legacy-path-eco-design-latest.html"

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

Many companies have integrated sustainability improvements into their core business strategies. Such trend is driven by the growing awareness of environmental matters and regulatory requirements like Corporate Sustainability Reporting Directive (CSRD), a regulatory framework proposed by the European Commission to enhance corporate transparency and ensure that companies provide comparable information to assess their sustainability performance.

Sustainability impacts numerous aspects of the life cycle management (LCM) of devices. This document discusses the benefits of leveraging existing devices modularity to introduce eco-designed components in the networks while being able to assess the gains in sustainability.

The motivation of this approach is the urgent need to start decreasing resource consumption by simply replacing devices components. This  approach can be viewed as a very basic use case of GREEN-bof {{GREEN-BOF}} approach.

# Network and devices modularity

Networks and their devices are modular by design to cope with manufacturing and operational constraints. Existing devices are going to be progressively replaced with more sustainable products. Both will co-exist in the networks as there is a balance to be found between the increased lifetime of existing devices and their replacement with eco-design devices {{SUST-INS}}.

The same approach applies at the same time to individual devices: legacy devices will include progressively more and more eco-designed hardware components.

Eco-design means that the products include environmental considerations throughout their entire lifecycle to reduce their environmental impact. In France they are based on General Reference Base for Eco-Design in digital services ("RGESN") at https://ecoresponsable.numerique.gouv.fr/publications/referentiel-general-ecoconception/.

Eco-design can be summarized as the concepts and current practices related to the integration of environmental aspects into every stage of a product lifecycle. This starts at product design and development [ISO/TR 14062:2002 ]

The upgrade of legacy devices with eco-designed cards can be separate in 2 categories:

 * "Simple" update : The adaptation is simple, a card is 'just' replaced with another one which consumes significantly less power by itself when running and which required fewer resources during its manufacturing and its deployment.

 * "Complex" update: The replacement of the card requires the adding or the update of software components to enable dynamic power consumption.

# Simple Update

Network operators have been updating their devices' components for decades. Consequently, replacement with eco-designed components can be begun immediately as there is no dependency on management solutions. The assessment of environmental and power gains can be done manually or with ad hoc scripts from the datasheets of the manufacturer or using an ad hoc process.

It is clear that information for doing static assessment is spread over many mediums or OPS interfaces (datasheet, Web URL, CLI , YANG, MIB, IPFIX ...). A proposal consists in documenting how to do static assessment for a set of devices and components based on volunteering {{GREEN-BOF}}.

In the mid-term, in a way to scale the assessment, inventory {{IVY-WG}} requires distinguishing legacy devices which include eco-designed components and eco-designed components inside legacy devices. This must not delay the initial deployment of eco-designed components in legacy devices described above.

## Simple Software Update

Software modularity increases with the generalisation of continuous development and deployment approaches. Power consumption of current software components of network devices is rarely evaluated. They can be updated immediately 'just' by replacing with another one which consumes significantly less power by itself.

It might seem inappropriate to try to decrease the power consumption of a software component as intuitively it is only doing what is expected, so this can't be reduced. However, software does not always use resources optimally and software updates can significantly improve or degrade performance and resource consumption.

This exists for assessing power efficiency of Web application components with good results. As an example, GreenIT is available as a browser plugin https://github.com/cnumr/GreenIT-Analysis.

# Complex Update

Currently network devices are mostly always-on. The design of their software components do not include dynamic power management.

The update of legacy networks and devices to support dynamic power management is a complex topic because it impacts the different type of components:

  * hardware components must support variation of power, of bit rate or only being shutdown and restarted
  * firmware components must expose monitoring and actionable functions to software components
  * software components must be updated or added to operate these new capabilities

Legacy hardware components are rarely designed to be stopped and restarted. The rhythm of start/stop supported by such components must be documented to prevent wrong usage of their real capacity. This must be present in the datasheet or exposed by the components themselves.

# Improve measurement methods

In the short-term, as promoted by the GREEN-BoF, the device level assessment requires datamodels augmentation {{IVY-WG}} to expose these capabilities and configuration updates first, and metrics to measure the power consumption {{POWEFF}} second.

Hackathon sessions can be used to compare assessment methods.

# Security Considerations

The tracking of LCM information may reveal device usage information.

Device inventory can be used by attackers when assessing a system for vulnerable components.

# IANA Considerations

At this step this document has no IANA actions.

--- back

# Acknowledgments
{:numbered="false"}

TODO acknowledge.
