<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Scholarship Matcher</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;800&display=swap" rel="stylesheet">
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        body {
            font-family: 'Poppins', sans-serif;
        }
        .animate-pulse-slow {
            animation: pulse 3s infinite;
        }
        .fade-in {
            animation: fadeIn 1.5s ease-out;
        }
        .slide-in {
            animation: slideIn 1.2s ease-out;
        }
        @keyframes fadeIn {
            0% { opacity: 0; transform: translateY(20px); }
            100% { opacity: 1; transform: translateY(0); }
        }
        @keyframes slideIn {
            0% { opacity: 0; transform: translateX(-100%); }
            100% { opacity: 1; transform: translateX(0); }
        }
    </style>
    <script>
        function showResults() {
            const gpa = document.getElementById('gpa').value;
            if (gpa) {
                document.getElementById('homepage').style.display = 'none';
                document.getElementById('results-page').style.display = 'block';
            }
        }
        function showDetails(detailsId) {
            document.getElementById('results-page').style.display = 'none';
            document.getElementById(detailsId).style.display = 'block';
        }
        function showApplicationForm() {
            document.querySelectorAll('.details-page').forEach(el => el.style.display = 'none');
            document.getElementById('application-form').style.display = 'block';
        }
    </script>
</head>
<body class="bg-gradient-to-r from-indigo-500 via-purple-500 to-pink-500 min-h-screen flex items-center justify-center p-6">
    <div id="homepage" class="text-center text-white max-w-4xl">
        <h1 class="text-6xl font-extrabold mb-6 animate-pulse-slow drop-shadow-lg">
            Welcome to <span class="text-yellow-300">Scholarship Matcher</span>
        </h1>
        <p class="text-2xl mb-8 leading-relaxed drop-shadow-md">
            Discover the best scholarships tailored to your academic profile.
        </p>
        <input type="number" id="gpa" placeholder="Enter your GPA" class="px-4 py-2 rounded-md text-gray-800 mb-4">
        <br>
        <button onclick="showResults()" class="px-8 py-4 bg-yellow-500 hover:bg-yellow-600 transition-all rounded-xl text-2xl font-semibold shadow-2xl drop-shadow-xl transform hover:scale-105 active:scale-95">
            Find Scholarships Now
        </button>
    </div>

    <div id="results-page" class="hidden bg-gradient-to-r from-blue-500 via-green-500 to-teal-500 min-h-screen flex flex-col items-center p-6">
        <div class="text-center text-white max-w-4xl mb-10">
            <h1 class="text-5xl font-extrabold mb-4 fade-in">Scholarship Results</h1>
            <p class="text-xl mb-8 fade-in">Here are the scholarships that match your academic profile.</p>
            <button onclick="location.reload()" class="inline-block px-6 py-3 bg-yellow-500 hover:bg-yellow-600 transition rounded-md font-semibold text-lg shadow-md fade-in">
                Back to Home
            </button>
        </div>

        <section class="grid grid-cols-1 md:grid-cols-2 gap-8 max-w-5xl w-full slide-in">
            <div class="bg-white p-6 rounded-lg shadow-lg hover:shadow-2xl transition transform hover:-translate-y-1">
                <h3 class="text-2xl font-bold mb-2">Science Excellence Scholarship</h3>
                <p class="mb-4">Available for students pursuing Science degrees with a minimum GPA of 3.5.</p>
                <button onclick="showDetails('science-details')" class="text-blue-500 hover:underline">Learn More</button>
            </div>

            <div class="bg-white p-6 rounded-lg shadow-lg hover:shadow-2xl transition transform hover:-translate-y-1">
                <h3 class="text-2xl font-bold mb-2">Arts and Humanities Grant</h3>
                <p class="mb-4">Ideal for students in History, Literature, and related fields. No GPA requirement.</p>
                <button onclick="showDetails('arts-details')" class="text-blue-500 hover:underline">Learn More</button>
            </div>
        </section>
    </div>

    <div id="science-details" class="hidden text-white p-10 details-page">
        <h2 class="text-4xl font-bold mb-4">Science Excellence Scholarship</h2>
        <p class="mb-4">Eligibility: Students with a GPA of 3.5+ pursuing Science degrees.</p>
        <p class="mb-4">Application Deadline: June 30, 2025</p>
        <button onclick="showApplicationForm()" class="text-yellow-400 hover:underline">Apply Now</button>
    </div>

    <div id="arts-details" class="hidden text-white p-10 details-page">
        <h2 class="text-4xl font-bold mb-4">Arts and Humanities Grant</h2>
        <p class="mb-4">Eligibility: Students in History, Literature, and related fields.</p>
        <p class="mb-4">No minimum GPA requirement.</p>
        <button onclick="showApplicationForm()" class="text-yellow-400 hover:underline">Apply Now</button>
    </div>

    <div id="application-form" class="hidden text-white p-10">
        <h2 class="text-4xl font-bold mb-4">Scholarship Application Form</h2>
        <form class="space-y-4">
            <input type="text" placeholder="Full Name" class="w-full p-2 rounded text-gray-800">
            <input type="email" placeholder="Email" class="w-full p-2 rounded text-gray-800">
            <textarea placeholder="Why do you deserve this scholarship?" class="w-full p-2 rounded text-gray-800"></textarea>
            <button type="submit" class="px-8 py-2 bg-yellow-500 hover:bg-yellow-600 transition-all rounded-xl text-xl font-semibold shadow-lg transform hover:scale-105 active:scale-95">
                Submit Application
            </button>
        </form>
    </div>

</body>
</html>
