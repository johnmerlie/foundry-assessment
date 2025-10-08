# Foundry Assessment

This project describes the requirements for a skills assessment for a Foundry Solutions Engineer.

## Prerequisites

Completing this assessment requires access to the Foundry platform. A free developer tier account can be obtained by navigating to [](https://build.palantir.com/) and following the 'Sign up' workflow at the top of the page.

Access should take roughly ~20 minutes including account setup and instance provisioning, but YMMV.

In order to sign up, a user will need:

- An email address and a phone number for 2FA with a one-time passcode
- An ID card from one of the countries listed, which is verified by a third-party (Stripe)
- A valid credit card which is also used for validation with Stripe but is not charged

After completing this, an email is sent confirming registration.

Within about 10 minutes, the Foundry instance should be created and instructions provided for logging in

## Assessment

The remaining sections of the document describe the requirements and expectations for completing the assessment.

### Company Background

Meridian Bakery Supply Co. is a regional food ingredients distributor operating two distribution centers in Cleveland and Atlanta. They supply 50+ different ingredients (flour varieties, sweeteners, fats, flavorings, packaging materials) to commercial bakeries across the Southeast. Materials are sourced from 20+ vendors with varying prices, lead times (5-14 days), and minimum order quantities. The procurement team currently manages reorders manually using spreadsheets, leading to frequent stockouts, emergency orders at premium prices, and inconsistent vendor selection. Your job is to build a data-driven system that monitors inventory levels across both plants, recommends optimal vendor selection balancing cost and lead time based on urgency, generates alerts when materials hit reorder points, and gives the procurement team an interface to review recommendations and approve purchase orders.

### What You're Building

An operational system with three core components:

- Data pipelines that calculate consumption rates, inventory health, and vendor recommendations
- An ontology layer modeling Materials, Plants, Vendors, etc.
- A Workshop application where procurement teams can see alerts, review vendor options with cost comparisons, and take action

### Data Provided

The data you'll use for the assessment is in the `data` directory of the repository, and contains 8 CSV files representing a variety of historical data associated with the business.

- consumption_history.csv (daily consumption records for 180 days)
- inventory_levels.csv (daily snapshots for 90 days)
- materials.csv (50 materials with categories, costs, reorder points)
- plants.csv (2 plants)
- purchase_order_history.csv (12 months of orders with on-time delivery data)
- vendor_communications.csv (500+ rows of communication history with vendors including delivery issues, quality complaints, price negotiations, and operational notes)
- vendor_material_pricing.csv (price, MOQ, and lead time by vendor-material pair)
- vendors.csv (20 vendors with payment terms and preferred status)

### Technical Requirements

Your solution should demonstrate proficiency with Foundry's core capabilities:

- Pipelines: Transform raw data using appropriate tools
- Model Integration: Build a simple recommendation model that informs future demand or influences vendor selection - focus on integrating it into the workflow, not ML sophistication or accuracy
- Unstructured Data Processing: Extract insights from vendor communications and incorporate them into your recommendation logic
- Ontology: Define business objects with properties and relationships
- Application: Create an operations-focused interface that enables the alert → review → action workflow
- Platform features: Leverage Foundry-specific capabilities
- We're intentionally leaving implementation details open - show us how you'd approach this problem.

## Evaluation

The evaluation will involve demonstrating your solution to a group of Foundry users and answering questions about implementation, approach, and outcomes.
