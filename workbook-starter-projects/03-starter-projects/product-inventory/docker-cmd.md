<h1>Building and Running Product Inventory Service in Docker</h1>

<p>This example shows how to build a Docker image for a Flask-based Product Inventory microservice and run it inside a container using the <b>Python</b> image.</p>

<h2>🚀 Build Command</h2>
<pre><code>docker build -t product-inventory .
</code></pre>

<h2>📊 Build Output</h2>
<pre><code>[+] Building 2.5s (11/11) FINISHED
 => [internal] load build definition from Dockerfile
 => [internal] load metadata for docker.io/library/python:3.8-slim
 => [internal] load .dockerignore
 => [1/5] FROM docker.io/library/python:3.8-slim
 => [2/5] WORKDIR /app
 => [3/5] COPY requirements.txt .
 => [4/5] RUN pip install -r requirements.txt
 => [5/5] COPY inventory_api.py .
 => exporting to image
 => naming to docker.io/library/product-inventory:latest
 => unpacking to docker.io/library/product-inventory:latest
</code></pre>

<h2>🚀 Run Command</h2>
<pre><code>docker run --network ecommerce-network --name product-inventory product-inventory
</code></pre>

<h2>📊 Example Output</h2>
<pre><code> * Serving Flask app 'inventory_api' (lazy loading)
 * Environment: production
   WARNING: This is a development server. Do not use it in a production deployment.
   Use a production WSGI server instead.
 * Debug mode: off
 * Running on all addresses.
   WARNING: This is a development server. Do not use it in a production deployment.
 * Running on http://172.19.0.6:3002/ (Press CTRL+C to quit)
</code></pre>

<h2>🌐 Access in Browser</h2>
<p>Since the Flask service runs on <code>3002</code> inside the container, mapped directly to <code>3002</code> on your host machine, open:</p>
<pre><code>http://localhost:3002/
</code></pre>

<h2>⚠️ Key Points</h2>
<ol>
  <li><b>Dockerfile</b>
    <ul>
      <li>Uses <code>python:3.8-slim</code> as the base image.</li>
      <li>Sets the working directory to <code>/app</code>.</li>
      <li>Installs dependencies from <code>requirements.txt</code>.</li>
      <li>Copies <code>inventory_api.py</code> into the container.</li>
    </ul>
  </li>
  <li><b>Build</b>
    <ul>
      <li><code>docker build -t product-inventory .</code> creates the image tagged <code>product-inventory</code>.</li>
    </ul>
  </li>
  <li><b>Run</b>
    <ul>
      <li><code>docker run --network ecommerce-network --name product-inventory product-inventory</code> starts the container and attaches it to the <code>ecommerce-network</code> so it can communicate with other microservices.</li>
      <li>The service runs on port <code>3002</code> inside the container.</li>
    </ul>
  </li>
</ol>

<h2>✅ Summary</h2>
<p>By defining a Dockerfile, building the image, and running the container with network connectivity, you can package and execute your Product Inventory microservice seamlessly inside Docker and integrate it with other services in the E‑Commerce application.</p>
