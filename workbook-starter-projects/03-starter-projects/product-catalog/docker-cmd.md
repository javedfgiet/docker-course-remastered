<h1>Building and Running Product Catalog Service in Docker</h1>

<p>This example shows how to build a Docker image for a Node.js-based Product Catalog microservice and run it inside a container using the <b>Node.js</b> image.</p>

<h2>🚀 Build Command</h2>
<pre><code>docker build -t product-catalog .
</code></pre>

<h2>📊 Build Output</h2>
<pre><code>[+] Building 9.3s (11/11) FINISHED
 => [internal] load build definition from Dockerfile
 => [internal] load metadata for docker.io/library/node:14
 => [internal] load .dockerignore
 => [1/5] FROM docker.io/library/node:14
 => [2/5] WORKDIR /app
 => [3/5] COPY package*.json .
 => [4/5] RUN npm install
 => [5/5] COPY . .
 => exporting to image
 => naming to docker.io/library/product-catalog:latest
 => unpacking to docker.io/library/product-catalog:latest
</code></pre>

<h2>🚀 Run Command</h2>
<pre><code>docker run --network ecommerce-network --name product-catalog product-catalog
</code></pre>

<h2>📊 Example Output</h2>
<pre><code>Product Catalog microservice is running on port 3001
</code></pre>

<h2>🌐 Access in Browser</h2>
<p>Since the Product Catalog service runs on <code>3001</code> inside the container, mapped directly to <code>3001</code> on your host machine, open:</p>
<pre><code>http://localhost:3001/
</code></pre>

<h2>⚠️ Key Points</h2>
<ol>
  <li><b>Dockerfile</b>
    <ul>
      <li>Uses <code>node:14</code> as the base image.</li>
      <li>Sets the working directory to <code>/app</code>.</li>
      <li>Copies <code>package.json</code> and installs dependencies with <code>npm install</code>.</li>
      <li>Copies the rest of the project files into the container.</li>
    </ul>
  </li>
  <li><b>Build</b>
    <ul>
      <li><code>docker build -t product-catalog .</code> creates the image tagged <code>product-catalog</code>.</li>
    </ul>
  </li>
  <li><b>Run</b>
    <ul>
      <li><code>docker run --network ecommerce-network --name product-catalog product-catalog</code> starts the container and attaches it to the <code>ecommerce-network</code> so it can communicate with other microservices.</li>
      <li>The service runs on port <code>3001</code> inside the container.</li>
    </ul>
  </li>
</ol>

<h2>✅ Summary</h2>
<p>By defining a Dockerfile, building the image, and running the container with network connectivity, you can package and execute your Product Catalog microservice seamlessly inside Docker and integrate it with other services in the E‑Commerce application.</p>
