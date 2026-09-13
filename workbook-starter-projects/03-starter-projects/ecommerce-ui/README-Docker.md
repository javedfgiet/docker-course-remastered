<h1>Building and Running E‑Commerce UI in Docker</h1>

<p>This example shows how to build a Docker image for a full‑stack E‑Commerce UI project (Node.js server + React client) and run it inside a container.</p>

<h2>🚀 Build Command</h2>
<pre><code>docker build -t ecommerce-ui .
</code></pre>

<h2>📊 Build Output</h2>
<pre><code>[+] Building 114.7s (17/17) FINISHED
 => [internal] load build definition from Dockerfile
 => [internal] load metadata for docker.io/library/node:14
 => [internal] load .dockerignore
 => [1/11] FROM docker.io/library/node:14
 => [2/11] WORKDIR /app
 => [3/11] COPY server /app/server
 => [4/11] WORKDIR /app/server
 => [5/11] RUN npm install
 => [6/11] WORKDIR /app
 => [7/11] COPY client /app/client
 => [8/11] WORKDIR /app/client
 => [9/11] RUN npm install
 => [10/11] RUN npm run build
 => [11/11] WORKDIR /app/server
 => exporting to image
 => naming to docker.io/library/ecommerce-ui:latest
 => unpacking to docker.io/library/ecommerce-ui:latest
</code></pre>

<h2>🚀 Run Command</h2>
<pre><code>docker run -p 4000:4000 --name ecommerce-ui ecommerce-ui
</code></pre>

<h2>📊 Example Output</h2>
<pre><code>Server is running on port 4000
</code></pre>

<h2>🌐 Access in Browser</h2>
<p>Since the Node.js server runs on <code>4000</code> inside the container and is mapped to <code>4000</code> on your host machine, open:</p>
<pre><code>http://localhost:4000/
</code></pre>

<h2>⚠️ Key Points</h2>
<ol>
  <li><b>Dockerfile</b>
    <ul>
      <li>Uses <code>node:14</code> as the base image.</li>
      <li>Installs dependencies for both <code>server</code> and <code>client</code>.</li>
      <li>Builds the React client with <code>npm run build</code>.</li>
      <li>Runs the Node.js server to serve the UI.</li>
    </ul>
  </li>
  <li><b>Build</b>
    <ul>
      <li><code>docker build -t ecommerce-ui .</code> creates the image tagged <code>ecommerce-ui</code>.</li>
    </ul>
  </li>
  <li><b>Run</b>
    <ul>
      <li><code>docker run -p 4000:4000 --name ecommerce-ui ecommerce-ui</code> starts the container and maps ports.</li>
      <li><code>--name</code> assigns a custom name to the container.</li>
    </ul>
  </li>
  <li><b>Browser Access</b>
    <ul>
      <li>Visit <code>http://localhost:4000/</code> to interact with the E‑Commerce UI.</li>
    </ul>
  </li>
</ol>

<h2>✅ Summary</h2>
<p>By defining a Dockerfile, building the image, and running the container with port mapping, you can package and execute your E‑Commerce UI seamlessly inside Docker and access it via your browser.</p>
