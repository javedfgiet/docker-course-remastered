<h1>Building and Running Node.js Grade Submission API in Docker</h1>

<p>This example shows how to build a Docker image for a Node.js application (<code>grade-submission-api</code>) and run it inside a container using the <b>Node.js</b> image.</p>

<h2>🚀 Build Command</h2>
<pre><code>docker build -t javedfgiet/grade-submision-api .
</code></pre>

<h2>📊 Build Output</h2>
<pre><code>[+] Building 0.7s (11/11) FINISHED
 => [internal] load build definition from Dockerfile
 => [internal] load metadata for docker.io/library/node:14
 => [internal] load .dockerignore
 => [1/6] FROM docker.io/library/node:14
 => [2/6] WORKDIR /app
 => [3/6] COPY package.json .
 => [4/6] COPY package-lock.json .
 => [5/6] RUN npm install
 => [6/6] COPY . .
 => exporting to image
 => naming to docker.io/javedfgiet/grade-submision-api:latest
 => unpacking to docker.io/javedfgiet/grade-submision-api:latest
</code></pre>

<h2>🚀 Run Command</h2>
<pre><code>docker run --name node-server --rm -p 3001:3000 javedfgiet/grade-submision-api
</code></pre>

<h2>📊 Example Output</h2>
<pre><code>Grade service is running on port 3000
Received GET request for grades
</code></pre>

<h2>🌐 Access in Browser</h2>
<p>Since port <code>3000</code> inside the container is mapped to port <code>3001</code> on your host machine, open:</p>
<pre><code>http://localhost:3001/
</code></pre>

<h2>⚠️ Key Points</h2>
<ol>
  <li><b>Dockerfile</b>
    <ul>
      <li>Defines the base image (<code>node:14</code>).</li>
      <li>Sets the working directory to <code>/app</code>.</li>
      <li>Copies <code>package.json</code> and <code>package-lock.json</code> for dependency installation.</li>
      <li>Runs <code>npm install</code> to install dependencies.</li>
      <li>Copies the rest of the project files into the container.</li>
    </ul>
  </li>
  <li><b>Build</b>
    <ul>
      <li><code>docker build -t javedfgiet/grade-submision-api .</code> creates the image tagged <code>javedfgiet/grade-submision-api</code>.</li>
    </ul>
  </li>
  <li><b>Run</b>
    <ul>
      <li><code>docker run --name node-server --rm -p 3001:3000 javedfgiet/grade-submision-api</code> starts the container and maps ports.</li>
      <li><code>--rm</code> ensures the container is removed after execution.</li>
      <li><code>--name</code> assigns a custom name to the container.</li>
    </ul>
  </li>
  <li><b>Browser Access</b>
    <ul>
      <li>Visit <code>http://localhost:3001/</code> to interact with the Grade Submission API.</li>
    </ul>
  </li>
</ol>

<h2>✅ Summary</h2>
<p>By defining a Dockerfile, building the image, and running the container with port mapping, you can package and execute your Node.js Grade Submission API seamlessly inside Docker and access it via your browser or API client.</p>
