
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Service Requests</title>
  <!-- Bootstrap CSS -->
  <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css">
  <!-- Custom CSS -->
  <style>
    body {
      background-color: #009170;
    }
    .jumbotron {
      background-color: #007bff;
      color: #fff;
      padding: 2rem;
    }
    .lead {
      color: #fff;
    }
    .card {
      margin-bottom: 20px;
    }
    .google-form-iframe {
      height: 600px; /* Adjust this height as needed */
    }
    .btn {
      color: #f8f9fa
        }
    .hidden {
      display: none;
    }
  </style>
</head>
<body>

  <div class="container">
    <div class="jumbotron">
      <h1 class="display-4">Service Requests</h1>
      <p class="lead">Welcome to our service request page. Please select the appropriate form below to submit your service request.</p>
      <!-- Buttons to show the forms -->
      <button id="showGolfCartForm" class="btn btn-primary">Golf Cart Service Request</button>
      <button id="showWorkMachineForm" class="btn btn-primary">Work/Lawn Machine Service Request</button>
    </div>

    <div class="row">
      <div class="col-md-6">
        <div class="card hidden" id="golfCartForm">
          <div class="card-body">
            <h5 class="card-title">Golf Cart Service Request Form</h5>
            <iframe class="google-form-iframe" src="https://docs.google.com/forms/d/e/1FAIpQLSeFVXGLgk_HBAB3mlrJu0QUmj0Y03HlSQrLgk-nwU70y1SvHw/viewform?embedded=true" frameborder="0" marginheight="0" marginwidth="0">Loading…</iframe>
          </div>
        </div>
      </div>
      <div class="col-md-6">
        <div class="card hidden" id="workMachineForm">
          <div class="card-body">
            <h5 class="card-title">Work/Lawn Machine Service Request Form</h5>
            <iframe class="google-form-iframe" src="https://docs.google.com/forms/d/e/1FAIpQLSdkLmgkvolM_RiL-2V1yLbyT3FdG1luws9ZglIxqHGIDs8xPw/viewform?embedded=true" frameborder="0" marginheight="0" marginwidth="0">Loading…</iframe>
          </div>
        </div>
      </div>
    </div>
  </div>

  <!-- Bootstrap JS -->
  <script src="https://code.jquery.com/jquery-3.5.1.slim.min.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.5.4/dist/umd/popper.min.js"></script>
  <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js"></script>
  <!-- Custom JS -->
  <script>
    document.getElementById('showGolfCartForm').addEventListener('click', function() {
      var element = document.getElementById('golfCartForm');
      element.classList.toggle('hidden');
    });
    document.getElementById('showWorkMachineForm').addEventListener('click', function() {
      var element = document.getElementById('workMachineForm');
      element.classList.toggle('hidden');
    });
  </script>
</body>
</html>
