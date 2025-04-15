# AI_Data_Search

AI Search for indexing and Querying Data

To use Azure Cognitive Search for indexing and querying data in the context of an online store, follow these step-by-step instructions:

### Step 1: Set Up Azure Resources

1. **Access the Azure Portal:**
   - Open your web browser and navigate to the Azure Portal.

2. **Create Azure AI Search Resource:**
   - Click on "Create a resource" in the left-hand panel.
   - Search for "Azure Cognitive Search" and select it from the results.
   - Click "Create" and fill in the necessary details such as service name, subscription, resource group, location, and pricing tier (Basic, Standard, or Storage Optimized).
   - Review your settings and click "Create" to provision the service.

3. **Create Azure AI Services Resource:**
   - Go back to the Azure Portal home page.
   - Click on "Create a resource" and search for "Azure AI Services."
   - Create a new AI Services resource in the same location as your Azure AI Search resource.
   - Fill in the required details and select the pricing tier (Standard S0).
   - Review and create the resource.

4. **Create a Storage Account:**
   - In the Azure Portal, click "Create a resource" and search for "Storage account."
   - Create a new storage account with a unique name, select the same resource group, and choose the location.
   - Set performance to Standard and redundancy to Locally-redundant storage (LRS).
   - Review and create the storage account.

### Step 2: Prepare and Upload Data

1. **Configure Storage Account:**
   - Navigate to your storage account and enable "Allow Blob anonymous access" under the configuration settings.
   - Save the changes.

2. **Create a Container:**
   - In the storage account, create a new container named `product-reviews` with public access set to "Container."

3. **Upload Data:**
   - Prepare your dataset of product reviews, descriptions, and other relevant data for your online store.
   - Upload the data files to the `product-reviews` container in your storage account.

### Step 3: Index the Data

1. **Import Data into Azure AI Search:**
   - Go to your Azure AI Search resource and select "Import data."
   - Choose "Azure Blob Storage" as the data source and connect to your storage account.
   - Select the `product-reviews` container and configure the data extraction settings.

2. **Add Cognitive Skills:**
   - Attach your Azure AI Services resource to enrich the data with cognitive skills like sentiment analysis, key phrase extraction, and more.
   - Configure the skillset to include relevant enrichments for product data, such as extracting product features or customer sentiment.

3. **Create Index and Indexer:**
   - Define the index schema, including fields for filtering and searching, such as product name, category, price, and customer reviews.
   - Create an indexer to automate the data import process.

### Step 4: Query the Data

1. **Use Search Explorer:**
   - In the Azure AI Search resource, open the Search Explorer.
   - Write and test queries using JSON format to validate the index quality.

2. **Example Queries:**
   - To retrieve all products:
     ```json
     {
         "search": "*",
         "count": true
     }
     ```
   - To filter by product category (e.g., electronics):
     ```json
     {
         "search": "category:'electronics'",
         "count": true
     }
     ```
   - To filter by customer sentiment (e.g., positive reviews):
     ```json
     {
         "search": "sentiment:'positive'",
         "count": true
     }
     ```

### Step 5: Review and Optimize

1. **Review Knowledge Store:**
   - Check the enriched data stored in the knowledge store for insights and projections related to product features and customer feedback.

2. **Optimize Search Experience:**
   - Continuously test and adjust the index and queries to improve search relevance and performance, ensuring customers can easily find products and information.

### Conclusion

Using Azure Cognitive Search for an online store allows you to transform raw product data into actionable insights, enhancing the shopping experience by providing intuitive and contextual search results. This setup helps customers find products quickly and efficiently, improving overall satisfaction and decision-making.
