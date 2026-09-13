<h1>Running Full E‑Commerce Application in Docker</h1>

<p>This example shows how to run the complete E‑Commerce application where the React frontend (UI) connects to multiple backend microservices (Profile Management, Contact Support, Shipping & Handling, Product Inventory, Product Catalog, and Order Management) via a Docker network.</p>

<h2>🔗 Create a Docker Network</h2>
<pre><code>docker network create ecommerce-network
</code></pre>

<h2>🚀 Run Backend Microservices</h2>
<pre><code>docker run --rm --network ecommerce-network --name profile-management profile-management
docker run --rm --network ecommerce-network --name contact-support-team contact-support-team
docker run --rm --network ecommerce-network --name shipping-and-handling shipping-and-handling
docker run --rm --network ecommerce-network --name product-inventory product-inventory
docker run --rm --network ecommerce-network --name product-catalog product-catalog
docker run --rm --network ecommerce-network --name order-management \
  -e PRODUCT_INVENTORY_API_HOST=http://product-inventory \
  -e PRODUCT_CATALOG_API_HOST=http://product-catalog \
  -e SHIPPING_HANDLING_API_HOST=http://shipping-and-handling \
  order-management
</code></pre>

<h2>🚀 Run Frontend (E‑Commerce UI)</h2>
<pre><code>docker run --rm -p 4000:4000 \
  -e REACT_APP_PROFILE_API_HOST=http://profile-management \
  -e REACT_APP_CONTACT_API_HOST=http://contact-support-team \
  -e REACT_APP_SHIPPING_API_HOST=http://shipping-and-handling \
  -e REACT_APP_INVENTORY_API_HOST=http://product-inventory \
  -e REACT_APP_PRODUCT_API_HOST=http://product-catalog \
  -e REACT_APP_ORDER_API_HOST=http://order-management \
  --name ecommerce-container \
  --network ecommerce-network \
  ecommerce-ui
</code></pre>

<h2>📊 Example Output</h2>
<pre><code>Server is running on port 4000
</code></pre>

<h2>🌐 Access in Browser</h2>
<p>Since the React UI runs on <code>4000</code> inside the container and is mapped to <code>4000</code> on your host machine, open:</p>
<pre><code>http://localhost:4000/
</code></pre>

<h2>⚠️ Key Points</h2>
<ol>
  <li><b>Network</b>
    <ul>
      <li>All containers are attached to <code>ecommerce-network</code> so they can resolve each other by name.</li>
      <li>Environment variables in the UI container tell React where each backend service lives.</li>
    </ul>
  </li>
  <li><b>Backend Services</b>
    <ul>
      <li><code>profile-management</code> → Authentication API (port 3003).</li>
      <li><code>contact-support-team</code> → Support service (port 8000).</li>
      <li><code>shipping-and-handling</code> → Shipping service (port 8080).</li>
      <li><code>product-inventory</code> → Inventory service (port 3002).</li>
      <li><code>product-catalog</code> → Catalog service (port 3001).</li>
      <li><code>order-management</code> → Order service (port 9090).</li>
    </ul>
  </li>
  <li><b>Frontend</b>
    <ul>
      <li>React UI runs on port <code>4000</code> and communicates with all backend services via environment variables.</li>
    </ul>
  </li>
</ol>

<h2>✅ Summary</h2>
<p>By creating a Docker network and running all microservices plus the React UI container on it, you deploy a fully functional E‑Commerce application. The frontend portal allows users to interact with authentication, product catalog, inventory, shipping, support, and order management seamlessly.</p>
