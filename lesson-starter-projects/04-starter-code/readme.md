<h1>Building and Running Java App in Docker</h1>

<p>This example shows how to build a Docker image for a Java application and run it inside a container using the <b>OpenJDK</b> image.</p>

<h2>🚀 Build Command</h2>
<pre><code>docker build -t java-app .
</code></pre>

<h2>📊 Build Output</h2>
<pre><code>[+] Building 77.3s (9/9) FINISHED
 => [internal] load build definition from Dockerfile
 => [internal] load metadata for docker.io/library/openjdk:28-ea-oraclelinux9
 => [internal] load .dockerignore
 => [1/3] FROM docker.io/library/openjdk:28-ea-oraclelinux9
 => [2/3] WORKDIR /app/
 => [3/3] COPY . .
 => exporting to image
 => naming to docker.io/library/java-app:latest
 => unpacking to docker.io/library/java-app:latest
</code></pre>

<h2>🚀 Run Command</h2>
<pre><code>docker run --rm --name java-app-container java-app
</code></pre>

<h2>📊 Example Output</h2>
<pre><code>     ____.  _________   _________
    |    | /  _  \   \ /   /  _  \
    |    |/  /_\  \   Y   /  /_\  \
 /\__|    /    |    \     /    |    \
 \________\____|__  /\___/\____|__  /
                  \/              \/
</code></pre>

<h2>⚠️ Key Points</h2>
<ol>
  <li><b>Dockerfile</b>
    <ul>
      <li>Defines the base image (<code>openjdk:28-ea-oraclelinux9</code>).</li>
      <li>Sets the working directory to <code>/app</code>.</li>
      <li>Copies project files into the container.</li>
    </ul>
  </li>
  <li><b>Build</b>
    <ul>
      <li><code>docker build -t java-app .</code> creates the image tagged <code>java-app</code>.</li>
    </ul>
  </li>
  <li><b>Run</b>
    <ul>
      <li><code>docker run --rm --name java-app-container java-app</code> starts the container and executes the Java app.</li>
      <li><code>--rm</code> ensures the container is removed after execution.</li>
      <li><code>--name</code> assigns a custom name to the container.</li>
    </ul>
  </li>
</ol>

<h2>✅ Summary</h2>
<p>By defining a Dockerfile, building the image, and running the container, you can package and execute your Java application seamlessly inside Docker.</p>
