<h1>Building and Running Ruby App in Docker</h1>

<p>This example shows how to build a Docker image for a Ruby application and run it inside a container using the <b>Ruby</b> image.</p>

<h2>🚀 Build Command</h2>
<pre><code>docker build -t ruby-app .
</code></pre>

<h2>📊 Build Output</h2>
<pre><code>[+] Building 1.7s (8/8) FINISHED
 => [internal] load build definition from Dockerfile
 => [internal] load metadata for docker.io/library/ruby:3.0
 => [internal] load .dockerignore
 => [1/3] FROM docker.io/library/ruby:3.0
 => [2/3] WORKDIR /app
 => [3/3] COPY . .
 => exporting to image
 => naming to docker.io/library/ruby-app:latest
 => unpacking to docker.io/library/ruby-app:latest
</code></pre>

<h2>🚀 Run Command</h2>
<pre><code>docker run --rm --name ruby-app-container ruby-app
</code></pre>

<h2>📊 Example Output</h2>
<pre><code>+--------------------------------------------------------------------------+
| Strive not to be a success, but rather to be of value. - Albert Einstein |
+--------------------------------------------------------------------------+
</code></pre>

<h2>⚠️ Key Points</h2>
<ol>
  <li><b>Dockerfile</b>
    <ul>
      <li>Defines the base image (<code>ruby:3.0</code>).</li>
      <li>Sets the working directory to <code>/app</code>.</li>
      <li>Copies project files into the container.</li>
    </ul>
  </li>
  <li><b>Build</b>
    <ul>
      <li><code>docker build -t ruby-app .</code> creates the image tagged <code>ruby-app</code>.</li>
    </ul>
  </li>
  <li><b>Run</b>
    <ul>
      <li><code>docker run --rm --name ruby-app-container ruby-app</code> starts the container and executes the Ruby app.</li>
      <li><code>--rm</code> ensures the container is removed after execution.</li>
      <li><code>--name</code> assigns a custom name to the container.</li>
    </ul>
  </li>
</ol>

<h2>✅ Summary</h2>
<p>By defining a Dockerfile, building the image, and running the container, you can package and execute your Ruby application seamlessly inside Docker.</p>
