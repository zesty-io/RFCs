# RFC 0013 - IGACC Workflow

## Summary

IGACC (idea > goal > activity > completion > communication) is a workflow to refine the process of creating product improvements. The workflow starts with an idea and ends with communication to the customer.

## Motivation

All development teams have a workflow. Some work better for others at different sizes, office setups, team distribution etc., and it is a highly subjective and opinionated subject. We are going to clearly define a workflow in this RFC for engineers at Zesty.io. This will be a public document for both our internal team and external community to understand how the product evolves.

Our team need to adopt a workflow that is relevant to our product and customers.

# Description

The IGACC workflow is comprised of 5 stages. The stages are setup to take an idea end to end from discussion to production. Between the ends, validation, planning, work assignment, and communication plans are made.

## IGACC WorkFlow

1. **Stage 1:** **Idea** is discussed and validated
 	* Origination should occur from one of these areas
		* Customer feature request
		* Internal team (usually based on industry need)
		* A requirement from the product roadmap
		* Bug or System Flaw requires a fundamental redesign
	* Idea is documented in a place that those discussing it all have access to
	* Idea discussion should lead to one of three possible outcomes:
 		* a) Idea stays an idea for refinement (stays in Stage 1)
		* b) Idea is converted to a Goal (proceeds to Stage 2)
		* c) Idea is turned down (terminated, documented, and removed from the flow)
2. **Stage 2:** A **Goal** is formed from the Idea
	* Goal is named and entered into the *Goal Queue*
	* Goals are assigned to an owner
	* Goals owner writes an RFCs and cover high level scope, dependencies, roadblocks etc.
	* Goal is discussed with a needs analysis, and given a target date
3. **Stage 3:** Goal **Activity** begins
	* Goal leaves the queue and enters the active state
 	* Goal owner reviews RFC, builds task List
	* Task list is reviewed with Goal Owner's manager
	* Time is allocated to job task list, tasks are assigned to team members, and job is placed into roadmap.
	* Team members start working against tasks to completion
4. **Stage 4:** Goal is **Completed**
	* Goal Owner and manager review the entirety of the Goal (GO may need more activity to refine, which mean back to Stage 3)
	* Goal is documented by the Goal Owner for both end user and internal consumption
	* Goal Owner communicates launch plan to team
5. **Stage 5:** **Communication** to the customer
	* Evaluate the impact of the completed work for these areas
	 	* Business impact
		* Recruitment
		* Development Evangelism
		* Community
		* Sales and Marketing
	* Affected users are notified to help them apply value to their existing product usage
	* The market is alerted to help organizations understand prospective product usage


## IGACC Terms

**Product**: Software a user system can interact with.

**Idea**: The concept of change or addition that add value to a product.

**Goal**: the overarching tasks of an idea, that when complete, produce a component, feature, or concept of a product.

**RFC**: Request for Comments (RFC) is a document that summarizes an Idea, and lays the foundation to describe the goal and tasks of the goal. This document is intended to be reviewed and commented on by peers to strengthen the idea for better usage and to refine the goal tasks for more accurate resource allocation.

**GO** *(Gee-Oh)*: Goal Owner (GO) is the person responsible for documenting, organizing, and seeing a goal through completion.

**Task**: Description of a job that when combined with other jobs, they describe the entirety of a Goal.

**Active Goals**: Where Goals being worked on are tracked.

**Goal Queue**: Where Goals are developed and stored. This can be in a project management software or a simple spreadsheet.
