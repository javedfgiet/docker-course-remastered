<h1>Building and Running Profile Management (Authentication API) in Docker</h1>

<p>This example shows how to build a Docker image for a Node.js Authentication API service and run it inside a container using the <b>Node.js</b> image.</p>

<h2>🚀 Build Command</h2>
<pre><code>docker build -t profile-management .
</code></pre>

<h2>📊 Build Output</h2>
<pre><code>[+] Building 7.6s (11/11) FINISHED
 => [internal] load build definition from Dockerfile
 => [internal] load metadata for docker.io/library/node:14
 => [internal] load .dockerignore
 => [1/5] FROM docker.io/library/node:14
 => [2/5] WORKDIR /app
 => [3/5] COPY package*.json .
 => [4/5] RUN npm install
 => [5/5] COPY . .
 => exporting to image
 => naming to docker.io/library/profile-management:latest
 => unpacking to docker.io/library/profile-management:latest
</code></pre>

<h2>🚀 Run Command</h2>
<pre><code>docker run --rm --network ecommerce-network --name profile-management profile-management
</code></pre>

<h2>📊 Example Output</h2>
<pre><code>Authentication API is running on port 3003
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
      <li><code>docker build -t profile-management .</code> creates the image tagged <code>profile-management</code>.</li>
    </ul>
  </li>
  <li><b>Run</b>
    <ul>
      <li><code>docker run --rm --network ecommerce-network --name profile-management profile-management</code> starts the container and attaches it to the <code>ecommerce-network</code> so it can communicate with other services (e.g., UI, product service, etc.).</li>
      <li><code>--rm</code> ensures the container is removed after execution.</li>
      <li><code>--name</code> assigns a custom name to the container.</li>
    </ul>
  </li>
  <li><b>Service</b>
    <ul>
      <li>The Authentication API runs on port <code>3003</code> inside the container.</li>
    </ul>
  </li>
</ol>

<h2>✅ Summary</h2>
<p>By defining a Dockerfile, building the image, and running the container with network connectivity, you can package and execute your Profile Management Authentication API seamlessly inside Docker and integrate it with other microservices in the E‑Commerce application.</p>
