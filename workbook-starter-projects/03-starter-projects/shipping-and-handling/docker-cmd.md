<h1>Building and Running Shipping and Handling Service in Docker</h1>

<p>This example shows how to build a Docker image for a Go-based Shipping and Handling microservice and run it inside a container using the <b>Golang</b> image.</p>

<h2>🚀 Build Command</h2>
<pre><code>docker build -t shipping-and-handling .
</code></pre>

<h2>📊 Build Output</h2>
<pre><code>[+] Building 92.8s (9/9) FINISHED
 => [internal] load build definition from Dockerfile
 => [internal] load metadata for docker.io/library/golang:1.20
 => [internal] load .dockerignore
 => [1/3] FROM docker.io/library/golang:1.20
 => [2/3] WORKDIR /app
 => [3/3] COPY main.go .
 => exporting to image
 => naming to docker.io/library/shipping-and-handling:latest
 => unpacking to docker.io/library/shipping-and-handling:latest
</code></pre>

<h2>🚀 Run Command</h2>
<pre><code>docker run --network ecommerce-network --name shipping-and-handling shipping-and-handling
</code></pre>

<h2>📊 Example Output</h2>
<pre><code>Server is running on port 8080...
</code></pre>

<h2>⚠️ Key Points</h2>
<ol>
  <li><b>Dockerfile</b>
    <ul>
      <li>Uses <code>golang:1.20</code> as the base image.</li>
      <li>Sets the working directory to <code>/app</code>.</li>
      <li>Copies <code>main.go</code> into the container.</li>
    </ul>
  </li>
  <li><b>Build</b>
    <ul>
      <li><code>docker build -t shipping-and-handling .</code> creates the image tagged <code>shipping-and-handling</code>.</li>
    </ul>
  </li>
  <li><b>Run</b>
    <ul>
      <li><code>docker run --network ecommerce-network --name shipping-and-handling shipping-and-handling</code> starts the container and attaches it to the <code>ecommerce-network</code> so it can communicate with other microservices (e.g., UI, profile management, etc.).</li>
      <li>The service runs on port <code>8080</code> inside the container.</li>
    </ul>
  </li>
</ol>

<h2>✅ Summary</h2>
<p>By defining a Dockerfile, building the image, and running the container with network connectivity, you can package and execute your Shipping and Handling microservice seamlessly inside Docker and integrate it with other services in the E‑Commerce application.</p>
