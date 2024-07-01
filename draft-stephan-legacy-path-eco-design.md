---
title: "legacy Modularity Usage for Eco-conception"
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
 -
   ins: E. Stephan
   name: Emile Stephan
   organization: Orange
   street: 2, avenue Pierre Marzin
   city: Lannion
   code: 22300
   country: France
   email: emile.stephan@gmail.com

 -
   name: Toby Lorne
   email: toby@toby.codes

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

This document discusses the usage of inventory-maintained information for assessing the adaptation of existing devices to eco-design. This assessment is driven by the weight of the manufacturing in the sustainability cost with regard to the power consumption.

--- middle

# Introduction

Many companies have integrated sustainability improvements into their core business strategies. Such trend is driven by the growing awareness of environmental matters and regulatory requirements like Corporate Sustainability Reporting Directive (CSRD), a regulatory framework proposed by the European Commission to enhance corporate transparency and ensure that companies provide comparable information to assess their sustainability performance.

Sustainability impacts numerous aspects of the life cycle management (LCM) of devices. This document discusses the benefits of leveraging existing devices modularity to introduce eco-designed components in the networks while being able to assess the gains in sustainability.

The motivation of this approach is the urgent need to start decreasing resource consumption by simply replacing devices components. This  approach can be viewed as a very basic use case of GREEN-bof {{GREEN-BOF}} approach.

# Network and Devices Modularity

Many Networks and networking devices (e.g., routers, switches, or Network Functions (NFs)) are designed with some modularity to cope with manufacturing and operational constraints. However, the modularity level is a still implementation and deployment specific. It is expected that legacy devices will be progressively replaced with eco-design products. Both will co-exist in networks as there is a balance to find between the increase of the live duration of existing devices and their replacement with eco-design devices {{SUST-INS}}.

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

# Path Toward Dynamic Assessement

In the short-term, as promoted by several discussions in the GREEN-BoF mailing list, the device level assessment requires datamodels augmentation {{IVY-WG}} to expose these capabilities and configuration updates first, and metrics to measure the power consumption {{POWEFF}} second.

In parallel it should document the minimum information (readable and parsable) about the parts of a legacy device which migrated to sustainability.

Hackathon sessions can be used to compare assessment methods based either on inventory metadata or metrics.

# Legacy Device and Energy efficiency

Legacy network devices energy efficiency monitoring and control differ from end-user devices.

As they are alway powered, network devices power consumption is taked in account during the dimensioning of a network. The operational phase, so after deployment, represents the main portion of a network device's total energy consumption. Nevertheless the manufacturing (including testing, ...) and the deployment (including transport...) is significant especially if the recycling is included.

On the opposite, end-user portable devices power consumption is explictly managed as they rely on battery and their maximum power consumtion occur during their manufacturing.

There are many other types of connected devices, none of these types of devices expose explicitly their energy efficiency.

## IETF EMAN WG

10 years ago the EMAN WG produced the specifications (requirements in rfc6988, framework in rfc7326, Energy Object Context MIB in rfc7461, Applicability Statement in rfc7603) for managing the energy produced and consumed by a broad types of network devices. The holistic approach includes standard for devices components rule and identifier.

10 years later, there isn't a commonly deployed framework for energy management of network devices components. Despite this, there migh be enough information in EMAN documents to standard the identification of components which "migrated to sustainability" in a legacy device.

Energy Object Context MIB, rfcrfc7461, is a reasonable starting point as it provides identification and context definitions which can be reused to describe these components.

# Use Cases

## Device replacement in a DC

Legacy hardware had to be replaced after reaching end-of-life (6+ years of constant use), replacement components for older hardware became scarcer.

Two objectives of the replacement:

1. reduce power consumption using newer hardware
2. reduce footprint in datacenter using denser devices (i.e., ~120 devices replaced by 30)

Before the project started it was difficult to estimate the power consumption reduction of the project. Only some components had idle consumption and max consumption power metrics, which would be used to compare inventory before and after.

During and after the project, active power consumption could only be measured from some components (e.g., cpu power consumption estimated via current and voltage sensors), and from the power distribution at each rack (where only a subset of devices were replaced).

One goal of the project could not be achieved: measure impact of increased density of devices (i.e., fan size impact moving from 1U to 2U devices which can be attributed to cooling) due to insufficient granularity of power consumption metrics (at component level).

Standardization of power consumption metrics (e.g. idle/max) for inventory would improve measurement for legacy hardware replacement projects. Improved power delivery designs inside racks already improves ability to measure real-time device power consumption, this allows device replacement projects to accurately measure impact. Devices reporting granular per-component power consumption metrics would allow component replacement projects to accurately measure reduction.

## Embedded Carbon

In the pursuit to asses the network is essential to understand the 'embedded carbon' of ICT equipment, which represents the greenhouse gas emissions associated with a product's entire lifecycle. A Life Cycle Assessment (LCA), conforming to international standards such as ISO 14040 and ISO 14044, is employed to model these impacts across multiple categories, from cradle to grave, please refer to Sustainability Insights draft {{SUST-INS}}.

For smartphones, approximately 80% of lifetime CO2e emissions are attributed to the production phase, underscoring the significance of manufacturing in the device's embedded carbon. In contrast, networking equipment not only incurs a substantial portion of its embedded carbon during production and testing but also during its operational life, including periods of idle power.

Vendors are increasingly focusing on reducing the energy consumption of networking equipment, both in operation and throughout the production process. Modular design and a circular closed-loop approach for component return, repair, recovery, and reuse are instrumental in decreasing the raw materials and emissions required for new components, thereby reducing the embedded carbon.

Embedded carbon is typically estimated based on energy consumption at each lifecycle stage, as direct measurement is often impractical. This estimation is crucial for organizations and consumers making environmentally responsible choices and for manufacturers striving to minimize the carbon footprint of their products. By selecting materials and processes with lower associated GHG emissions and improving design, manufacturers can significantly reduce energy consumption and, consequently, embedded carbon.

When accounting for the energy consumption of network equipment and components, it is important to consider not only the idle power but also the energy allocated to the manufacturing phase. This comprehensive approach ensures that the embedded energy—and by extension, the embedded carbon—of each piece of equipment is accurately reflected in environmental impact assessments.

# Security Considerations

The tracking of LCM information may reveal device usage information.

Device inventory can be used by attackers when assessing a system for vulnerable components.

# IANA Considerations

At this step this document has no IANA actions.

--- back

# Acknowledgments
{:numbered="false"}

TODO acknowledge.
