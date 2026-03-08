# BUSINESS SCENARIO
`SupplyChain360`, a fast-growing retail distribution company in the United States, manages product distribution for hundreds of retail stores across the country.

Over the past year, the company has been experiencing **serious operational inefficiencies** in its supply chain:
- Stores frequently run **out of stock** of popular products.
- Warehouses report **overstocked inventory** for slow-moving items.
- Delivery delays are becoming common.
- Management cannot accurately answer simple questions like:
    - Which products are causing the most stockouts?
    - Which warehouses are inefficient?
    - Which suppliers consistently deliver late?

The biggest issue is **data fragmentation**. Operational data is spread across multiple systems:
- Warehouse inventory systems
- Logistics shipment records
- Supplier delivery logs
- Store sales data

Each team manages its own data, and reports are manually compiled in spreadsheets every week. By the time leadership receives insights, the data is already outdated.

The company leadership has decided to build a **Unified Supply Chain Data Platform** that centralizes operational data and enables efficient analytics to improve:
- Inventory planning
- Supplier performance monitoring
- Shipment tracking
- Demand forecasting

You have been hired as a Data Engineer to design and implement this platform.

If successful, your platform will allow the company to **reduce stockouts, optimize inventory**, and improve delivery efficiency, potentially saving **millions of dollars annually**.

# DATA SOURCES
You have been granted access to several operational datasets from different systems.

Each dataset represents a **different operational domain of the supply chain.**

### Product Catalog
- Description: Master dataset containing product information sold across stores.
- Format: CSV
- Data Location: Stored in an **S3 Bucket on AWS**
- Frequency: Static dataset (rarely changes)

### Store Locations
- Description: Dataset containing information about retail store locations.
- Format: Google Spreadsheet
- Data Location: [Google Sheets](https://docs.google.com/spreadsheets/d/1y70rZ8qpPd5GJGgZYWwAR4mGAYn8aGGJynwm9GyEVnQ/edit?usp=sharing)
- Frequency: Static dataset

**Note**: You must **move the dataset to your own private Google Sheet** and configure a **Service Account** to programmatically extract the data via the **Google Sheets API**.

### Warehouse Inventory Snapshots
- Description: Daily inventory snapshot of each warehouse showing stock levels per product.
- Format: CSV
- Data Location: Stored in **S3**
- Frequency: Daily

