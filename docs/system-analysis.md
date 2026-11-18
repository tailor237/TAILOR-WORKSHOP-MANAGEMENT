# System Analysis - Tailor Workshop Management System (Group 13)

**Authors:** Njoke Randall Ndahseh (Analysis & Backend Lead) & Kwenchia Tangmoh Yannis (System Analyst)  
**Project:** Tailor Workshop Orders Management System  

## 1. Project Purpose
This system is designed to replace paper notebooks in a local tailoring workshop run by **1 Master Tailor** and **3 Apprentices**. It keeps track of customer body measurements, fabric details, orders for common garments (**shirts, traditional wear, material trousers, and school uniforms**), payment balances in **FCFA**, and delivery deadlines.

## 2. Workshop Users & Responsibilities
* **Master Tailor (Workshop Owner / Admin):**
  * Registers new customers and records their body measurements.
  * Logs garment orders, sets the total price in FCFA, and records advance deposits and remaining balances.
  * Assigns each order to one of the three apprentices.
  * Checks finished clothes and triggers SMS/WhatsApp reminders for pickup.
* **Apprentices (3 Staff Members):**
  * View only the orders assigned to them by the Master Tailor.
  * Update the production stage as they work on a garment.
  * Leave short notes if there is an issue (e.g., missing buttons, thread, or fabric shortage).

## 3. Order Production Workflow
Each order moves through the following stages from intake to collection:
1. **Pending Measurements:** Order created; waiting for customer measurements or fabric drop-off.
2. **Assigned:** Master Tailor hands the job over to Apprentice 1, 2, or 3.
3. **Cutting:** Apprentice measures and cuts the fabric.
4. **Sewing:** Apprentice is currently sewing and assembling the outfit.
5. **Fitting:** Garment is ready for the customer to try on for adjustments.
6. **Completed:** Final ironing done; SMS/WhatsApp reminder sent to customer for pickup and final FCFA balance payment.

## 4. Core Data Entities (Initial Database Design)
*(Note: Specific data types and table schemas will be finalized once Group 13 confirms the backend tech stack on Saturday.)*

* **Users:** `user_id`, `full_name`, `role` (`master_tailor` or `apprentice`), `phone_number`, `password_hash`
* **Customers:** `customer_id`, `full_name`, `phone_number`, `whatsapp_enabled`, `notes`
* **Measurements:** `measurement_id`, `customer_id`, `chest`, `waist`, `hips`, `shoulder`, `sleeve_length`, `trouser_length`, `neck`, `updated_at`
* **Orders:** `order_id`, `customer_id`, `assigned_apprentice_id`, `garment_type` (`shirt`, `traditional_wear`, `material_trousers`, `school_uniform`), `fabric_description`, `total_price_fcfa`, `amount_paid_fcfa`, `remaining_balance_fcfa`, `status`, `due_date`, `reminder_sent`, `created_at`
