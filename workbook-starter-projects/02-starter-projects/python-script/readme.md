<h1>Building and Running Python App in Docker</h1>

<p>This example shows how to build a Docker image for a Python application and run it inside a container using the <b>Python</b> image. It also demonstrates passing command-line arguments and exploring the container interactively.</p>

<h2>🚀 Build Command</h2>
<pre><code>docker build -t python-app .
</code></pre>

<h2>📊 Build Output</h2>
<pre><code>[+] Building 1.9s (8/8) FINISHED
 => [internal] load build definition from Dockerfile
 => [internal] load metadata for docker.io/library/python:3.8-slim
 => [internal] load .dockerignore
 => [1/3] FROM docker.io/library/python:3.8-slim
 => [2/3] WORKDIR /app
 => [3/3] COPY . .
 => exporting to image
 => naming to docker.io/library/python-app:latest
 => unpacking to docker.io/library/python-app:latest
</code></pre>

<h2>🚀 Run Command</h2>
<pre><code>docker run --rm --name python-app-container python-app
</code></pre>

<h2>📊 Example Output</h2>
<pre><code>Command-line arguments:
I am Javedfgiet
</code></pre>

<h2>🔍 Interactive Debugging</h2>
<pre><code>docker run -it --rm --name python-app-container python-app /bin/sh
# ls
Dockerfile  script.py
# python script I am JavedAhmad
python: can't open file 'script': [Errno 2] No such file or directory
# python script.py I am javed Ahamd
Command-line arguments:
I
am
javed
Ahamd
# exit
</code></pre>

<h2>⚠️ Key Points</h2>
<ol>
  <li><b>Dockerfile</b>
    <ul>
      <li>Defines the base image (<code>python:3.8-slim</code>).</li>
      <li>Sets the working directory to <code>/app</code>.</li>
      <li>Copies project files into the container.</li>
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
  <li><b>Interactive Debugging</b>
    <ul>
      <li>Use <code>-it</code> with <code>/bin/sh</code> to open a shell inside the container.</li>
      <li>Verify files with <code>ls</code> and run scripts directly.</li>
      <li>Ensure you reference the correct filename (<code>script.py</code> not <code>script</code>).</li>
    </ul>
  </li>
</ol>

<h2>✅ Summary</h2>
<p>By defining a Dockerfile, building the image, and running the container, you can package and execute your Python application seamlessly inside Docker. Interactive mode allows you to debug and confirm that files are correctly copied and executed.</p>
