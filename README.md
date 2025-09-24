
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>EduBoard - Student Dashboard</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: #f5f7fb;
    }
    .container {
      display: flex;
      min-height: 100vh;
    }
    /* Sidebar */
    .sidebar {
      width: 200px;
      background: #2563eb;
      color: #fff;
      padding: 20px;
    }
    .sidebar h2 {
      margin-top: 0;
    }
    .sidebar a {
      display: block;
      color: #fff;
      text-decoration: none;
      margin: 10px 0;
      cursor: pointer;
    }
    .sidebar a:hover {
      text-decoration: underline;
    }
    /* Main */
    .main {
      flex: 1;
      padding: 20px;
    }
    header {
      background: #fff;
      padding: 10px 20px;
      margin-bottom: 20px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    }
    .cards {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
      gap: 10px;
      margin-bottom: 20px;
    }
    .card {
      background: #fff;
      padding: 15px;
      border-radius: 8px;
      text-align: center;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    }
    table {
      width: 100%;
      border-collapse: collapse;
      background: #fff;
      margin-bottom: 20px;
    }
    th, td {
      padding: 10px;
      border: 1px solid #ddd;
      text-align: left;
    }
    .deadlines, .profile {
      background: #fff;
      padding: 15px;
      border-radius: 8px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
      margin-bottom: 20px;
    }
    /* Hide all sections by default */
    .section {
      display: none;
    }
    .active-section {
      display: block;
    }
  </style>
</head>
<body>
  <div class="container">
    <!-- Sidebar -->
    <nav class="sidebar">
      <h2>EduBoard</h2>
      <a onclick="showSection('dashboard')">Dashboard</a>
      <a onclick="showSection('subjects')">Subjects</a>
      <a onclick="showSection('attendance')">Attendance</a>
      <a onclick="showSection('profile')">Profile</a>
      <a onclick="showSection('settings')">Settings</a>
    </nav>

    <!-- Main Content -->
    <div class="main">
      <header>
        <h2 id="header-title">Dashboard</h2>
        <span>🔔</span>
      </header>

      <!-- Sections -->
      <div id="dashboard" class="section active-section">
        <div class="cards">
          <div class="card">
            <h3>GPA</h3>
            <p>8.6</p>
          </div>
          <div class="card">
            <h3>Attendance</h3>
            <p>92%</p>
          </div>
          <div class="card">
            <h3>Assignments</h3>
            <p>2 Due</p>
          </div>
          <div class="card">
            <h3>Credits</h3>
            <p>18</p>
          </div>
        </div>
      </div>

      <div id="subjects" class="section">
        <h3>Subject Progress</h3>
        <table>
          <tr>
            <th>Subject</th>
            <th>Progress</th>
            <th>Grade</th>
          </tr>
          <tr>
            <td>Data Structures</td>
            <td>78%</td>
            <td>A-</td>
          </tr>
          <tr>
            <td>Database Systems</td>
            <td>92%</td>
            <td>A</td>
          </tr>
          <tr>
            <td>Networks</td>
            <td>61%</td>
            <td>B+</td>
          </tr>
        </table>
      </div>

      <div id="attendance" class="section">
        <h3>Attendance</h3>
        <p>Your average attendance is <strong>92%</strong>. Keep it up!</p>
      </div>

      <div id="profile" class="section">
        <div class="profile">
          <h3>Profile</h3>
          <p><strong>Name:</strong> Ramanathan M</p>
          <p><strong>Roll No:</strong> 20BCE123</p>
          <p><strong>Email:</strong> ramanathan@example.com</p>
          <p><strong>College:</strong> IIT Example</p>
        </div>
      </div>

      <div id="settings" class="section">
        <h3>Settings</h3>
        <p>Here you can manage your account settings.</p>
      </div>

      <div class="deadlines">
        <h3>Upcoming Deadlines</h3>
        <p>24 Sep - DS Lab 4 Submission</p>
        <p>26 Sep - DB Quiz</p>
        <p>30 Sep - Project Proposal</p>
      </div>
    </div>
  </div>

  <script>
    function showSection(id) {
      // Hide all sections
      document.querySelectorAll('.section').forEach(sec => sec.classList.remove('active-section'));
      // Show the clicked one
      document.getElementById(id).classList.add('active-section');
      // Update header title
      document.getElementById('header-title').innerText = id.charAt(0).toUpperCase() + id.slice(1);
    }
  </script>
</body>
</html>
