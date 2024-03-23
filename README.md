<!DOCTYPE html>
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
      background-color: #f8f9fa;
    }
    .jumbotron {
      background-color: #007bff;
      color: #fff;
      padding: 2rem;
    }
    .card {
      margin-bottom: 20px;
    }
    /* Adjust iframe height */
    .google-form-iframe {
      height: 600px; /* Adjust this height as needed */
    }
  </style>
</head>
<body>

  <div class="container">
    <div class="jumbotron">
      <h1 class="display-4">Service Requests</h1>
      <p class="lead">Welcome to our service request page. Please select the appropriate form below to submit your service request.</p>
    </div>

    <div class="row">
      <div class="col-md-6">
        <div class="card">
          <div class="card-body">
            <h5 class="card-title">Golf Cart Service Request Form</h5>
            <!-- Embed Plumbing Service Request Form -->
            <iframe class="google-form-iframe" src="https://docs.google.com/forms/d/e/1FAIpQLSeFVXGLgk_HBAB3mlrJu0QUmj0Y03HlSQrLgk-nwU70y1SvHw/viewform?embedded=true" frameborder="0" marginheight="0" marginwidth="0">Loading…</iframe>
          </div>
        </div>
      </div>
      <div class="col-md-6">
        <div class="card">
          <div class="card-body">
            <h5 class="card-title">Work/La Service Request Form</h5>
            <!-- Embed Electrical Service Request Form -->
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
</body>
</html>
