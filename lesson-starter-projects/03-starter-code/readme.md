<h1>Building and Running Python App in Docker</h1>

<p>This example shows how to build a Docker image for a Python application (<code>python-app.py</code>) and run it inside a container.</p>

<h2>🚀 Build Command</h2>
<pre><code>docker build -t python-app .
</code></pre>

<h2>📊 Build Output</h2>
<pre><code>[+] Building 0.7s (8/8) FINISHED
 => [internal] load build definition from Dockerfile
 => [internal] load metadata for docker.io/library/python:3.8-slim
 => [internal] load .dockerignore
 => [1/3] FROM docker.io/library/python:3.8-slim
 => [2/3] WORKDIR /app
 => [3/3] COPY python-app.py /app
 => exporting to image
 => naming to docker.io/library/python-app:latest
 => unpacking to docker.io/library/python-app:latest
</code></pre>

<h2>🚀 Run Command</h2>
<pre><code>docker run --rm --name python-app-container python-app
</code></pre>

<h2>📊 Example Output</h2>
<pre><code>    ____        _   _                  _
   |  _ \ _   _| |_| |__   ___  _ __  / \
   | |_) | | | | __| '_ \ / _ \| '_ \/  /
   |  __/| |_| | |_| | | | (_) | | | /\_/
   |_|    \__, |\__|_| |_|\___/|_| |_(_)
          |___/
</code></pre>

<h2>⚠️ Key Points</h2>
<ol>
  <li><b>Dockerfile</b>
    <ul>
      <li>Defines the base image (<code>python:3.8-slim</code>).</li>
      <li>Sets the working directory to <code>/app</code>.</li>
      <li>Copies <code>python-app.py</code> into the container.</li>
    </ul>
  </li>
  <li><b>Build</b>
    <ul>
      <li><code>docker build -t python-app .</code> creates the image tagged <code>python-app</code>.</li>
    </ul>
  </li>
  <li><b>Run</b>
    <ul>
      <li><code>docker run --rm --name python-app-container python-app</code> starts the container and executes the Python app.</li>
      <li><code>--rm</code> ensures the container is removed after execution.</li>
      <li><code>--name</code> assigns a custom name to the container.</li>
    </ul>
  </li>
</ol>

<h2>✅ Summary</h2>
<p>By defining a Dockerfile, building the image, and running the container, you can package and execute your Python application seamlessly inside Docker.</p>
