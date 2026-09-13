<h1>Building and Running Spring Boot App in Docker</h1>

<p>This example shows how to build a Docker image for a Spring Boot application and run it inside a container using the <b>Maven + OpenJDK</b> image.</p>

<h2>🚀 Build Command</h2>
<pre><code>docker build -t springbotdemo .
</code></pre>

<h2>📊 Build Output</h2>
<pre><code>[+] Building 57.4s (8/8) FINISHED
 => [internal] load build definition from Dockerfile
 => [internal] load metadata for docker.io/library/maven:3.8-openjdk-18-slim
 => [internal] load .dockerignore
 => [1/3] FROM docker.io/library/maven:3.8-openjdk-18-slim
 => [2/3] WORKDIR /app/
 => [3/3] COPY /springboot-demo/ .
 => exporting to image
 => naming to docker.io/library/springbotdemo:latest
 => unpacking to docker.io/library/springbotdemo:latest
</code></pre>

<h2>🚀 Run Command</h2>
<pre><code>docker run --rm -p 8080:8080 --name sprintboot-container springbotdemo
</code></pre>

<h2>📊 Example Output</h2>
<pre><code>Downloaded from central: https://repo.maven.apache.org/maven2/org/apache/commons/commons-collections4/4.4/commons-collections4-4.4.jar (752 kB at 250 kB/s)
[INFO] Attaching agents: []

  .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::                (v3.2.0)
</code></pre>

<h2>🌐 Access in Browser</h2>
<p>Since port <code>8080</code> inside the container is mapped to port <code>8080</code> on your host machine, open:</p>
<pre><code>http://localhost:8080/
</code></pre>

<h2>⚠️ Key Points</h2>
<ol>
  <li><b>Dockerfile</b>
    <ul>
      <li>Defines the base image (<code>maven:3.8-openjdk-18-slim</code>).</li>
      <li>Sets the working directory to <code>/app</code>.</li>
      <li>Copies the Spring Boot project files into the container.</li>
    </ul>
  </li>
  <li><b>Build</b>
    <ul>
      <li><code>docker build -t springbotdemo .</code> creates the image tagged <code>springbotdemo</code>.</li>
    </ul>
  </li>
  <li><b>Run</b>
    <ul>
      <li><code>docker run --rm -p 8080:8080 --name sprintboot-container springbotdemo</code> starts the container and maps ports.</li>
      <li><code>--rm</code> ensures the container is removed after execution.</li>
      <li><code>--name</code> assigns a custom name to the container.</li>
    </ul>
  </li>
  <li><b>Browser Access</b>
    <ul>
      <li>Visit <code>http://localhost:8080/</code> to see the Spring Boot app running.</li>
    </ul>
  </li>
</ol>

<h2>✅ Summary</h2>
<p>By defining a Dockerfile, building the image, and running the container with port mapping, you can package and execute your Spring Boot application seamlessly inside Docker and access it via your browser.</p>
