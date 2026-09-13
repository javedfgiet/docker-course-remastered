<h1>Building and Running Contact Support Team Service in Docker</h1>

<p>This example shows how to build a Docker image for a Flask-based Contact Support Team microservice and run it inside a container using the <b>Python</b> image.</p>

<h2>🚀 Build Command</h2>
<pre><code>docker build -t contact-support-team .
</code></pre>

<h2>📊 Build Output</h2>
<pre><code>[+] Building 6.5s (10/10) FINISHED
 => [internal] load build definition from Dockerfile
 => [internal] load metadata for docker.io/library/python:3.8-slim
 => [internal] load .dockerignore
 => [1/5] FROM docker.io/library/python:3.8-slim
 => [2/5] WORKDIR /app
 => [3/5] COPY requirements.txt .
 => [4/5] RUN pip install -r requirements.txt
 => [5/5] COPY server.py .
 => exporting to image
 => naming to docker.io/library/contact-support-team:latest
 => unpacking to docker.io/library/contact-support-team:latest
</code></pre>

<h2>🚀 Run Command</h2>
<pre><code>docker run --rm --network ecommerce-network --name contact-support-team contact-support-team
</code></pre>

<h2>📊 Example Output</h2>
<pre><code> * Serving Flask app 'server' (lazy loading)
 * Environment: production
   WARNING: This is a development server. Do not use it in a production deployment.
   Use a production WSGI server instead.
 * Debug mode: off
 * Running on all addresses.
   WARNING: This is a development server. Do not use it in a production deployment.
 * Running on http://172.19.0.5:8000/ (Press CTRL+C to quit)
172.19.0.2 - - [13/Sep/2026 18:02:39] "GET /api/contact-message HTTP/1.1" 200 -
172.19.0.2 - - [13/Sep/2026 18:02:51] "POST /api/contact-submit HTTP/1.1" 200 -
172.19.0.2 - - [13/Sep/2026 18:02:53] "GET /api/contact-message HTTP/1.1" 200 -
</code></pre>

<h2>🌐 Access in Browser</h2>
<p>Since the Flask service runs on <code>8000</code> inside the container, mapped directly to <code>8000</code> on your host machine, open:</p>
<pre><code>http://localhost:8000/
</code></pre>

<h2>⚠️ Key Points</h2>
<ol>
  <li><b>Dockerfile</b>
    <ul>
      <li>Uses <code>python:3.8-slim</code> as the base image.</li>
      <li>Sets the working directory to <code>/app</code>.</li>
      <li>Installs dependencies from <code>requirements.txt</code>.</li>
      <li>Copies <code>server.py</code> into the container.</li>
    </ul>
  </li>
  <li><b>Build</b>
    <ul>
      <li><code>docker build -t contact-support-team .</code> creates the image tagged <code>contact-support-team</code>.</li>
    </ul>
  </li>
  <li><b>Run</b>
    <ul>
      <li><code>docker run --rm --network ecommerce-network --name contact-support-team contact-support-team</code> starts the container and attaches it to the <code>ecommerce-network</code> so it can communicate with other microservices.</li>
      <li><code>--rm</code> ensures the container is removed after execution.</li>
      <li><code>--name</code> assigns a custom name to the container.</li>
    </ul>
  </li>
  <li><b>Service</b>
    <ul>
      <li>The Contact Support Team service runs on port <code>8000</code> inside the container.</li>
      <li>Provides endpoints such as <code>/api/contact-message</code> (GET) and <code>/api/contact-submit</code> (POST).</li>
    </ul>
  </li>
</ol>

<h2>✅ Summary</h2>
<p>By defining a Dockerfile, building the image, and running the container with network connectivity, you can package and execute your Contact Support Team microservice seamlessly inside Docker and integrate it with other services in the E‑Commerce application.</p>
