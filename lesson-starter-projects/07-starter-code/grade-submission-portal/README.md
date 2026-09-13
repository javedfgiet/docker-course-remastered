<h1>Building and Running Flask Grade Submission Portal in Docker</h1>

<p>This example shows how to build a Docker image for a Flask-based Grade Submission Portal and run it inside a container using the <b>Python</b> image.</p>

<h2>🚀 Build Command</h2>
<pre><code>docker build -t javedfgiet/grade-submission-portal .
</code></pre>

<h2>📊 Build Output</h2>
<pre><code>[+] Building 25.1s (11/11) FINISHED
 => [internal] load build definition from Dockerfile
 => [internal] load metadata for docker.io/library/python:3.8-slim
 => [internal] load .dockerignore
 => [1/5] FROM docker.io/library/python:3.8-slim
 => [2/5] WORKDIR /app
 => [3/5] COPY requirements.txt .
 => [4/5] RUN pip install -r requirements.txt
 => [5/5] COPY . .
 => exporting to image
 => naming to docker.io/javedfgiet/grade-submission-portal:latest
 => unpacking to docker.io/javedfgiet/grade-submission-portal:latest
</code></pre>

<h2>🚀 Run Command</h2>
<pre><code>docker run --rm --name flask-app -p 5000:5001 javedfgiet/grade-submission-portal
</code></pre>

<h2>📊 Example Output</h2>
<pre><code> * Serving Flask app 'app' (lazy loading)
 * Environment: production
   WARNING: This is a development server. Do not use it in a production deployment.
   Use a production WSGI server instead.
 * Debug mode: on
 * Running on all addresses.
   WARNING: This is a development server. Do not use it in a production deployment.
 * Running on http://172.17.0.3:5001/ (Press CTRL+C to quit)
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 140-818-103
172.17.0.1 - - [13/Sep/2026 16:09:03] "GET / HTTP/1.1" 200 -
172.17.0.1 - - [13/Sep/2026 16:09:03] "GET /static/form-stylesheet.css HTTP/1.1" 200 -
172.17.0.1 - - [13/Sep/2026 16:09:04] "GET /favicon.ico HTTP/1.1" 404 -
</code></pre>

<h2>🌐 Access in Browser</h2>
<p>Since port <code>5001</code> inside the container is mapped to port <code>5000</code> on your host machine, open:</p>
<pre><code>http://localhost:5000/
</code></pre>

<h2>⚠️ Key Points</h2>
<ol>
  <li><b>Dockerfile</b>
    <ul>
      <li>Defines the base image (<code>python:3.8-slim</code>).</li>
      <li>Sets the working directory to <code>/app</code>.</li>
      <li>Copies <code>requirements.txt</code> and installs dependencies.</li>
      <li>Copies the rest of the project files into the container.</li>
    </ul>
  </li>
  <li><b>Build</b>
    <ul>
      <li><code>docker build -t javedfgiet/grade-submission-portal .</code> creates the image tagged <code>grade-submission-portal</code>.</li>
    </ul>
  </li>
  <li><b>Run</b>
    <ul>
      <li><code>docker run --rm --name flask-app -p 5000:5001 javedfgiet/grade-submission-portal</code> starts the container and maps ports.</li>
      <li><code>--rm</code> ensures the container is removed after execution.</li>
      <li><code>--name</code> assigns a custom name to the container.</li>
    </ul>
  </li>
  <li><b>Browser Access</b>
    <ul>
      <li>Visit <code>http://localhost:5000/</code> to interact with the Grade Submission Portal.</li>
    </ul>
  </li>
</ol>

<h2>✅ Summary</h2>
<p>By defining a Dockerfile, building the image, and running the container with port mapping, you can package and execute your Flask Grade Submission Portal seamlessly inside Docker and access it via your browser.</p>
