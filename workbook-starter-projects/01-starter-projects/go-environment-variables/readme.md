<h1>Running Go App in Docker</h1>

<p>This example shows how to run a Go application (<code>main.go</code>) inside a Docker container using the <b>Golang</b> image, while passing environment variables.</p>

<h2>🚀 Correct Command</h2>
<pre><code>docker run --rm -v "C:\Users\javed\source\repos\docker-course-remastered\workbook-starter-projects\01-starter-projects\go-environment-variables:/app/" -e MESSAGE="Hello From Docker" --name GoEnvironmentConatiner golang:1.16 go run /app/main.go
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
      <li>Maps your local folder (<code>go-environment-variables</code>) to <code>/app</code> inside the container.</li>
      <li>This makes <code>main.go</code> available to the container.</li>
    </ul>
  </li>
  <li><b>Environment variable</b>
    <ul>
      <li><code>-e MESSAGE="Hello From Docker"</code> passes the environment variable <code>MESSAGE</code> into the container.</li>
    </ul>
  </li>
  <li><b>Container name</b>
    <ul>
      <li><code>--name GoEnvironmentConatiner</code> assigns a custom name to the container.</li>
    </ul>
  </li>
  <li><b>Image</b>
    <ul>
      <li>Uses <code>golang:1.16</code> as the base image.</li>
    </ul>
  </li>
  <li><b>Script execution</b>
    <ul>
      <li>Runs the Go program with:
        <pre><code>go run /app/main.go</code></pre>
      </li>
    </ul>
  </li>
</ol>

<h2>📊 Example Output</h2>
<pre><code>Hello From Docker
</code></pre>

<h2>✅ Summary</h2>
<p>By mounting the project folder, naming the container, and passing environment variables, you can run your Go application seamlessly inside Docker and inject dynamic values into your program.</p>
