<h1>Building and Running Order Management Service in Docker</h1>

<p>This example shows how to build a Docker image for a Spring Boot-based Order Management microservice and run it inside a container using the <b>Maven + OpenJDK</b> image.</p>

<h2>🚀 Build Command</h2>
<pre><code>docker build -t order-management .
</code></pre>

<h2>📊 Build Output</h2>
<pre><code>[+] Building 79.4s (10/10) FINISHED
 => [internal] load build definition from Dockerfile
 => [internal] load metadata for docker.io/library/maven:3.8-openjdk-18-slim
 => [1/4] FROM docker.io/library/maven:3.8-openjdk-18-slim
 => [2/4] WORKDIR /app
 => [3/4] COPY . .
 => [4/4] RUN mvn install
 => exporting to image
 => naming to docker.io/library/order-management:latest
 => unpacking to docker.io/library/order-management:latest
</code></pre>

<h2>🚀 Run Command</h2>
<pre><code>docker run --network ecommerce-network \
  --name order-management \
  -e PRODUCT_INVENTORY_API_HOST=http://product-inventory \
  -e PRODUCT_CATALOG_API_HOST=http://product-catalog \
  -e SHIPPING_HANDLING_API_HOST=http://shipping-and-handling \
  order-management
</code></pre>

<h2>📊 Example Output</h2>
<pre><code>[INFO] Scanning for projects...
[INFO] Building order-management 0.0.1-SNAPSHOT
[INFO] --- spring-boot-maven-plugin:3.2.3:run (default-cli) @ order-management ---
 :: Spring Boot ::                (v3.2.3)

2026-09-13T18:41:53.978Z  INFO 62 --- [order-management] c.l.o.OrderManagementApplication : Starting OrderManagementApplication
2026-09-13T18:41:54.843Z  INFO 62 --- [order-management] TomcatWebServer  : Tomcat initialized with port 9090 (http)
2026-09-13T18:41:55.158Z  INFO 62 --- [order-management] TomcatWebServer  : Tomcat started on port 9090 (http) with context path ''
2026-09-13T18:41:55.164Z  INFO 62 --- [order-management] OrderManagementApplication : Started OrderManagementApplication
</code></pre>

<h2>🌐 Access in Browser</h2>
<p>The Order Management service runs on <code>9090</code> inside the container. Open:</p>
<pre><code>http://localhost:9090/
</code></pre>

<h2>⚠️ Key Points</h2>
<ol>
  <li><b>Dockerfile</b>
    <ul>
      <li>Uses <code>maven:3.8-openjdk-18-slim</code> as the base image.</li>
      <li>Sets the working directory to <code>/app</code>.</li>
      <li>Copies the project files and runs <code>mvn install</code> to build the Spring Boot application.</li>
    </ul>
  </li>
  <li><b>Build</b>
    <ul>
      <li><code>docker build -t order-management .</code> creates the image tagged <code>order-management</code>.</li>
    </ul>
  </li>
  <li><b>Run</b>
    <ul>
      <li><code>docker run --network ecommerce-network ...</code> starts the container and attaches it to the <code>ecommerce-network</code> so it can communicate with other microservices.</li>
      <li>Environment variables configure connections to <code>product-inventory</code>, <code>product-catalog</code>, and <code>shipping-and-handling</code> services.</li>
    </ul>
  </li>
  <li><b>Service</b>
    <ul>
      <li>The Order Management service runs on port <code>9090</code> inside the container.</li>
    </ul>
  </li>
</ol>

<h2>✅ Summary</h2>
<p>By defining a Dockerfile, building the image, and running the container with environment variables and network connectivity, you can package and execute your Order Management microservice seamlessly inside Docker and integrate it with other services in the E‑Commerce application.</p>
