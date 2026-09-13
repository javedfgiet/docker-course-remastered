<h1>Running Java App in Docker</h1>

<p>This example shows how to run a Java application (<code>JavaApp.jar</code>) inside a Docker container using the <b>OpenJDK</b> image.</p>

<h2>🚀 Correct Command</h2>
<pre><code>docker run --rm -v "C:\Users\javed\source\repos\docker-course-remastered\lesson-starter-projects\02-starter-code:/app/source" --name javatestcontainer openjdk:28-ea-oraclelinux9 java -cp /app/source/JavaApp.jar JavaApp
</code></pre>

<h2>⚠️ Key Points</h2>
<ol>
  <li><b>--rm flag</b>
    <ul>
      <li>Ensures the container is removed after execution.</li>
    </ul>
  </li>
  <li><b>Volume mount</b>
    <ul>
      <li>Maps your local folder (<code>02-starter-code</code>) to <code>/app/source</code> inside the container.</li>
      <li>This makes <code>JavaApp.jar</code> available to the container.</li>
    </ul>
  </li>
  <li><b>Container name</b>
    <ul>
      <li><code>--name javatestcontainer</code> assigns a custom name to the container.</li>
    </ul>
  </li>
  <li><b>Image</b>
    <ul>
      <li>Uses <code>openjdk:28-ea-oraclelinux9</code> as the base image.</li>
    </ul>
  </li>
  <li><b>Classpath execution</b>
    <ul>
      <li>Runs the JAR file with:
        <pre><code>java -cp /app/source/JavaApp.jar JavaApp</code></pre>
      </li>
    </ul>
  </li>
</ol>

<h2>📊 Example Output</h2>
<pre><code>     ____.  _________   _________
    |    | /  _  \   \ /   /  _  \
    |    |/  /_\  \   Y   /  /_\  \
 /\__|    /    |    \     /    |    \
 \________\____|__  /\___/\____|__  /
                  \/              \/
</code></pre>

<h2>✅ Summary</h2>
<p>By mounting the project folder, naming the container, and specifying the correct classpath, you can run your Java application seamlessly inside Docker.</p>
