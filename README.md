# QKart - Checkout Simplified

## Project Overview

QKart is an intelligent shopping cart engineered to redefine the retail checkout experience. The system tackles systemic inefficiencies in traditional retail environments, such as prolonged checkout queues, manual scanning inaccuracies, and poor inventory management. By integrating computer vision (CV) and Internet of Things (IoT) technologies, QKart provides automated item detection, real-time billing, and dynamic inventory synchronization.

The core of the QKart prototype is a Raspberry Pi 5 (4GB RAM) which acts as the primary processing unit. A lightweight, highly optimized YOLOv4-tiny model performs real-time object detection as items are placed into the cart. To ensure accuracy and mitigate errors, the system incorporates weight sensors with HX711 modules for a crucial layer of cross-verification. All transactional and inventory data are meticulously synchronized in real-time to a dedicated web application via a Firebase cloud database. This dual-validation mechanism enhances reliability and acts as a robust anti-theft measure.

## Motivation and Problem Statement

The retail industry faces pressure to innovate in response to customer expectations for convenience and efficiency. Traditional checkout systems suffer from long queues, billing errors, and poor inventory management, which negatively impacts profitability and customer loyalty. A 2022 McKinsey report highlighted that over 30% of shoppers abandon purchases due to long lines, resulting in billions of dollars in lost revenue annually.

QKart provides a cost-effective and automated solution to these issues. It eliminates the frustration of queues for shoppers by automatically detecting items and updating a real-time bill. For retailers, QKart automates the billing process, synchronizes stock data to the cloud, and minimizes human error. Unlike expensive existing solutions like RFID-based carts that require costly product tags, QKart's approach can reduce implementation costs by 60-70%.

## Novelty and Key Features

The QKart project is a novel advancement in retail automation due to its key innovations:

* *Seamless Self-Checkout Experience:* The system provides a completely automated, hands-free checkout by integrating computer vision for product identification and a real-time billing web application. This reduces wait times and allows retailers to cut down on labor costs.

* *Integrated Multi-Sensor Verification for Fraud Prevention:* The system incorporates a robust fraud prevention mechanism by combining a computer vision model with weight-based verification using HX711 modules. This dual-verification approach ensures high accuracy and prevents unbilled items from leaving the store.

* *Cost-Effective and Accessible Technology:* QKart provides a market-disrupting solution by leveraging affordable hardware, such as the Raspberry Pi 5, and open-source software. This makes sophisticated smart cart technology accessible to small-to-mid-sized retailers without significant capital investment.

## Technical Architecture

The QKart system operates on a distributed architecture with three key layers:

* *Hardware Layer:* Consists of physical components, including a Raspberry Pi 5, a high-resolution camera module, and four load cells connected to an HX711 amplifier to measure weight changes.

* *On-Cart Software Layer:* A Python script orchestrates the system, using OpenCV to manage the camera feed and a lightweight YOLOv4-tiny model for object detection. The model is converted to TensorFlow Lite for optimized performance on the Raspberry Pi 5.

* *Backend & User Interface Layer:* The cart communicates with a central backend server via a REST API built with Flask. The backend updates a central inventory database (PostgreSQL) and pushes real-time updates to the customer's web-based UI.

The system workflow is a seamless, event-driven process:
1.  *Cart Activation & Image Capture:* The cart is activated, and the camera captures an image of the item.
2.  *Object Detection & Verification:* The YOLO model detects the item, and its identity is cross-verified using the weight sensor data.
3.  *Data Synchronization:* If the item is validated, its information is stored locally (SQLite) and synchronized with the cloud database (Firebase).
4.  *User Interface & Payment:* The customer's mobile/web UI is updated with the new item list and total bill. The final payment is handled via a QR-based UPI payment system.
   
   <img width="388" height="706" alt="image" src="https://github.com/user-attachments/assets/72677106-cbe8-4c71-b392-78e3b0066d08" />


## Project Progress

The project is structured into several major phases, with significant progress made to date:

* *Phase I: Research & Planning:* Completed (Jan - Mar 2025).
* *Phase II: Hardware Assembly & Setup:* Completed (Mar - May 2025).
* *Phase III: Core Software & AI Development:* In Progress (May - Sep 2025).
    * *Model Training:* The YOLO model was trained and achieved a mean Average Precision (mAP) of 98.0% on the validation dataset.
      
      <img width="650" height="293" alt="image" src="https://github.com/user-attachments/assets/7f78809c-d7ae-4658-a542-86f85087bb64" />


      <img width="650" height="325" alt="image" src="https://github.com/user-attachments/assets/421d6737-c0ee-49d8-a464-7a2a2483bcca" />

    * *Inference Speed:* When converted to TensorFlow Lite, the model's inference time was an average of 94 milliseconds on the device.
      
      <img width="650" height="270" alt="image" src="https://github.com/user-attachments/assets/4dc3827b-8509-4e9e-915c-6be8c084c56e" />

* *Phase IV: Backend & UI Development:* Upcoming (Sep - Oct 2025).
* *Phase V: Testing, Optimization & Finalization:* Upcoming (Oct - Dec 2025).
  
  * <img width="650" height="523" alt="image" src="https://github.com/user-attachments/assets/9473115b-c383-44b8-9ef8-528c5fe52d0b" />


## Future Prospects

The QKart project aims to deliver a fully functional smart cart prototype. Future prospects for the project include:

* *Scalability:* The current prototype is designed for a limited number of products. Scaling the system would require a larger, more comprehensive dataset and a robust backend infrastructure.
* *Enhanced Features:* In the future, the system can be expanded to provide retailers with valuable real-time analytics on customer shopping trends.
* *Model Improvement:* Ongoing model training with a larger, more diverse dataset will further improve detection accuracy under various conditions.

## Team Members

* Abhimanyu Kumar (Regn. No: 102215021) 
* Arushi Gupta (Regn. No: 102206190) 
* Khushi Kaushal (Regn. No: 102206269) 
* Tanishka Bhatia (Regn. No: 102206217) 
* Uttkarsh Singh Pathania (Regn. No: 102215291)
