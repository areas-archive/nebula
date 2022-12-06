# Tutorial Layout

The following is a high-level overview of the markdown structure that all tutorials should contain. Make a note of the markdown heading sizes.


```
# Title
<Intro body>
# Prerequisites

# [Concept 1]

## [Sub-concept 1]

## [Sub-concept 2]

# [Concept 2]

## [Sub-concept 1]

## [Sub-concept 2]

# Cleanup

# Next Steps
```

## Section Breakdown

Below is an explanation of each section of a tutorial. You can have as many concepts and sub-concept headings as needed. For example purposes, the section breakdown will only use two sub-concepts.

| Section                 | Description                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|-------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Title                   | The name assigned to the tutorial. Aim for a title that is no longer than five words.                                                                                                                                                                                                                                                                                                                                                          |
| Intro Body              | The introduction sets the context for the tutorial and explains the challenge. The introduction must also provide the user with an explanation of what they will learn in this tutorial.                                                                                                                                                                                                                                                       |
| Prerequisites           | List out the required software or hardware the practitioner is required to have installed and available in order to complete the tutorial.                                                                                                                                                                                                                                                                                                     |
| Clone GitHub Repository | Most tutorials are expected to have a public GitHub repository containing a versioned copy of the tutorial code, if applicable. In this section, the user should be walked through the following commands:Cloning the repo (SSH/HTTP git clone command)Fetch updates if they already have the repository git fetchChanging directory locally to the repository folderCheckout the proper tagChange directory to the respective tutorial folder |
| [Concept]               | The title of one of main concepts of the tutorial. This can potentially be one out of several main concepts.  Example - “Configure the Environment”                                                                                                                                                                                                                                                                                            |
| [Sub-Concept]           | The tile of a child concept that stems from the parent concept.  Example - “Create Secondary Cluster” OR “App Model  Overview”                                                                                                                                                                                                                                                                                                                 |
| Cleanup                 | All tutorials should ideally be deployed through infrastructure as code (IaC), if applicable.  All resources deployed by the tutorial should be removed. It is our responsibility to help and provide guidance to the user on how to remove all resources. Sometimes this section is brief with a simple command such as `terraform destroy -auto-approve`                                                                                                  |
| Next Steps              | This section summarizes the key learning concepts and the actions the practitioner conducted. Additionally, this section should link to or suggest the next set of topics that the practitioner can dive into.                                                                                                                                                                                                                                     |

