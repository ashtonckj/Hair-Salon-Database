# SheepMe Salon Database Project
> **Note:** This project is part of an academic assignment.  
> The organisation, names, locations, and details in the background story are entirely fictional.

## 1. Organisation Background

**SheepMe Salon** is a hair salon founded by **Mr. Lim He Ping** in 2023, with its first outlet at **TARUMT Mall, Pulau Pinang**.  
It now operates **25 branches** across Malaysia:

- Pulau Pinang: 5 branches  
- Kuala Lumpur: 7 branches  
- Melaka: 3 branches  
- Johor Bahru: 5 branches  
- Pahang: 5 branches  

**Slogan:** *"SheepMe, Your Best Choice"*  

**Services provided:**
- Hair washing  
- Haircuts  
- Hair colouring  
- Hair treatment  
- Beauty treatments

The salon operates with professional hairstylists and beauticians, offering both appointments and walk-ins. Appointments can be made via phone or in person. A centralized appointment management system is used to:
- Avoid scheduling conflicts  
- Assign staff efficiently  
- Manage customer profiles (phone, gender, membership status)  
- Track payments and pricing  
- Maintain product inventory for services

---

## 2. Potential Problems / Opportunities

**Challenges:**
- Mismanagement of customer appointments  
- Inefficient staff allocation  
- Risk of overbooking and overlapping schedules  
- Possible decline in customer service quality

**Solution:**
- Implement a **centralized database system** to manage:
  - Customer appointments  
  - Staff schedules  
  - Service records  
  - Payment details  
- Automate routine tasks to:
  - Reduce manual errors  
  - Improve customer experience  
  - Increase operational efficiency

---

## 3. Business Rules

1. A customer may schedule one or many appointments, but each appointment only belongs to one customer.  
2. An appointment contains one or many appointment details, but each appointment detail only belongs to one appointment.  
3. A payment may contain one or many appointment details, but each appointment detail only belongs to one payment.  
4. An outlet may employ one or many staff, but each staff only belongs to one outlet.  
5. A staff may be assigned to one or many appointment details, but each appointment detail only belongs to one staff.  
6. A product may be used in one or many product services, but each product service only belongs to one product.  
7. A service may have one or many product services, but each product service only belongs to one service.  
8. A service may be assigned to one or many appointment details, but each appointment detail only belongs to one service.  

---

## 4. ERD Diagram

<img width="909" height="935" alt="image" src="https://github.com/user-attachments/assets/8a4af8ad-42da-47fe-9ea9-bcb46c10359c" />

---

## 5. Entities Listing in DBDL

```plaintext
CUSTOMER (cust_id, cust_name, cust_phone, cust_email, cust_gender, member_status)
APPOINTMENT (apt_code, apt_date, apt_starttime, apt_endtime, cust_id*)
APPOINTMENT_DETAILS (AptDetails_id, apt_code*, staff_id*, service_id*, payment_id*)
PAYMENT (payment_id, total_price, total_paid, payment_method, payment_discount)
OUTLETS (outlet_id, outlet_name, outlet_location, outlet_state, outlet_phone)
STAFF (staff_id, staff_name, staff_birth, staff_gender, staff_phone, staff_email, staff_address, outlet_id*)
SERVICE (service_id, service_name, service_desc, service_price, service_duration)
PRODUCT_SERVICE (ProService_id, pro_id*, service_id*)
PRODUCT (pro_id, pro_name, pro_desc, pro_qty, pro_volume, pro_UOM)
