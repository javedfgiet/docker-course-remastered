<h1>Grade Submission Application</h1>

<p>This project demonstrates a full-stack application where users can submit grades via a Flask portal (frontend) that connects to a Node.js API (backend). Both services are containerized and published to Docker Hub.</p>

<h2>📦 Docker Images</h2>
<ul>
  <li><b>Frontend (Portal)</b>: <code>javedfgiet/grade-submission-portal:latest</code></li>
  <li><b>Backend (API)</b>: <code>javedfgiet/grade-submission-api:latest</code></li>
</ul>

<h2>🚀 Build Commands</h2>
<pre><code>docker build -t javedfgiet/grade-submission-portal .
docker build -t javedfgiet/grade-submission-api .
</code></pre>

<h2>📤 Push to Docker Hub</h2>
<pre><code>docker push javedfgiet/grade-submission-portal
docker push javedfgiet/grade-submission-api
</code></pre>


<h2>✅ Summary</h2>
<p>By building, pushing, and running both containers on a shared Docker network, you deploy a fully functional Grade Submission application. The frontend portal allows users to submit details, while the backend API stores and retrieves grades.</p>
