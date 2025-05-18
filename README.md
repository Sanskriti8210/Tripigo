# Tripigo
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TRIPIGO</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-1BmE4kWBq78iYhFldvKuhfTAU6auU8tT94WrHftjDbrCEXSU1oBoqyl2QvZ6jIW3" crossorigin="anonymous">
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@fortawesome/fontawesome-free@6.1.1/css/all.min.css">
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f1f1f1;
        }
        .hero {
            background-image: linear-gradient(to bottom, #3498db, #2ecc71);
            padding: 200px 0;
            background-size: cover;
            background-position: center;
            color: #fff;
        }
        .budget-form {
            padding: 20px;
            background-color: #fff;
            border: 1px solid #ddd;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        .summary {
            padding: 20px;
            background-color: #dff0d8;
            border: 1px solid #ddd;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        .contact-form {
            padding: 20px;
            background-color: #fff;
            border: 1px solid #ddd;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        .footer {
            background-color: #333;
            color: #fff;
            padding: 20px;
            text-align: center;
        }
        nav {
            background-color: #3498db;
        }
        nav a {
            color: #fff;
        }
        .page {
            display: none;
        }
        .active {
            display: block;
        }
    </style>
</head>
<body>
    <nav class="navbar navbar-expand-lg navbar-light">
        <div class="container">
            <a class="navbar-brand" href="#home">Vacation Budget Tracker</a>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarSupportedContent">
                <ul class="navbar-nav ms-auto mb-2 mb-lg-0">
                    <li class="nav-item"><a class="nav-link" href="#" onclick="showPage('home')">Home</a></li>
                    <li class="nav-item"><a class="nav-link" href="#" onclick="showPage('budget-calculator')">Budget Calculator</a></li>
                    <li class="nav-item"><a class="nav-link" href="#" onclick="showPage('summary')">Summary</a></li>
                    <li class="nav-item"><a class="nav-link" href="#" onclick="showPage('contact')">Contact</a></li>
                    <li class="nav-item"><a class="nav-link" href="#" onclick="showPage('about')">About</a></li>
                </ul>
            </div>
        </div>
    </nav>

    <div id="home" class="page hero active">
        <div class="container">
            <h1 class="display-3">Welcome to TRIPIGO</h1>
            <p class="lead">Plan your trip and stay within your budget</p>
            <a href="#" class="btn btn-primary" onclick="showPage('budget-calculator')">Get Started</a>
        </div>
    </div>

    <div id="budget-calculator" class="page budget-form">
        <div class="container">
            <h2>Budget Calculator</h2>
            <form>
                <div class="mb-3">
                    <label for="trip-name" class="form-label">Trip Name:</label>
                    <input type="text" class="form-control" id="trip-name" placeholder="Enter trip name">
                </div>
                <div class="mb-3">
                    <label for="transportation-cost" class="form-label">Transportation Cost:</label>
                    <input type="number" class="form-control" id="transportation-cost" placeholder="Enter transportation cost">
                </div>
                <div class="mb-3">
                    <label for="accommodation-cost" class="form-label">Accommodation Cost:</label>
                    <input type="number" class="form-control" id="accommodation-cost" placeholder="Enter accommodation cost">
                </div>
                <div class="mb-3">
                    <label for="food-cost" class="form-label">Food Cost:</label>
                    <input type="number" class="form-control" id="food-cost" placeholder="Enter food cost">
                </div>
                <div class="mb-3">
                    <label for="activities-cost" class="form-label">Activities Cost:</label>
                    <input type="number" class="form-control" id="activities-cost" placeholder="Enter activities cost">
                </div>
                <div class="mb-3">
                    <label for="days" class="form-label">Number of Days:</label>
                    <input type="number" class="form-control" id="days" placeholder="Enter number of days">
                </div>
                <button type="button" class="btn btn-primary" id="calculate-budget">Calculate Budget</button>
            </form>
        </div>
    </div>

    <div id="summary" class="page summary">
        <div class="container">
            <h2>Summary</h2>
            <p id="total-cost"></p>
            <p id="transportation-display"></p>
            <p id="accommodation-display"></p>
            <p id="food-display"></p>
            <p id="activities-display"></p>
            <canvas id="myChart" width="400" height="400"></canvas>
        </div>
    </div>

    <div id="contact" class="page contact-form">
        <div class="container">
            <h2>Contact Us</h2>
            <form>
                <div class="mb-3">
                    <label for="name" class="form-label">Name:</label>
                    <input type="text" class="form-control" id="name" placeholder="Enter name">
                </div>
                <div class="mb-3">
                    <label for="email" class="form-label">Email:</label>
                    <input type="email" class="form-control" id="email" placeholder="Enter email">
                </div>
                <div class="mb-3">
                    <label for="message" class="form-label">Message:</label>
                    <textarea class="form-control" id="message" placeholder="Enter message"></textarea>
                </div>
                <button type="submit" class="btn btn-primary">Send Message</button>
            </form>
        </div>
    </div>

    <div id="about" class="page">
        <div class="container">
            <h2>About Us</h2>
            <p>Welcome to TRIPIGO, your trusted companion for planning stress-free 
               <br>and budget-friendly vacations. We understand that managing travel expenses can be
               <br> daunting, which is why we've developed a user-friendly platform to help you track
               <br> and calculate your vacation costs effortlessly.

                Our intuitive tool allows you to input various expenses—such as flights, 
                <br>accommodations, meals, activities, and miscellaneous costs—and automatically 
                <br>calculates your total budget. Whether you're planning a solo adventure, 
                <br>a family getaway, or a group trip, our tracker ensures you stay within your
                <br> financial means without compromising on fun.
                
                <br>
                <br>
                <br>
                Why Choose Us?<br>
                Comprehensive Expense Tracking: Monitor all aspects of your travel spending in one place.<br>
                
                Real-Time Calculations: Instantly see how each expense impacts your overall budget.<br>
                
                User-Friendly Interface: Designed for ease of use, even for first-time planners.<br>
                
                Accessible Anywhere: Plan and adjust your budget on-the-go from any device.<br>
                
                Join thousands of travelers who have turned their dream vacations into reality without financial stress.<br>
                 Start planning smarter today with [TRIPIGO]</p>
        </div>
    </div>
    <div class="footer">
        <div class="container">
            <p>&copy; 2023 Vacation Budget Tracker</p>
            <div>
                <a href="https://www.facebook.com" target="_blank" class="social-media"><i class="fa fa-facebook" aria-hidden="true"></i> Facebook</a>
                <a href="https://www.instagram.com" target="_blank" class="social-media"><i class="fa fa-instagram" aria-hidden="true"></i> Instagram</a>
                <a href="https://www.twitter.com" target="_blank" class="social-media"><i class="fa fa-twitter" aria-hidden="true"></i> Twitter</a>
                <a href="mailto:info@example.com" target="_blank" class="social-media"><i class="fa fa-envelope" aria-hidden="true"></i> Contact Us</a>
            </div>
        </div>
    </div>

    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-ka7Sk0Gln4gmtz2MlQnikT1wXgYsOg+OMhuP+IlRH9sENBO0LRn5q+8nbTov4+1p" crossorigin="anonymous"></script>
    <script>
        function showPage(pageId) {
            const pages = document.querySelectorAll('.page');
            pages.forEach(page => {
                page.classList.remove('active');
            });
            const page = document.getElementById(pageId);
            page.classList.add('active');
        }

        const calculateBudget = document.getElementById('calculate-budget');
        const tripName = document.getElementById('trip-name');
        const transportationCost = document.getElementById('transportation-cost');
        const accommodationCost = document.getElementById('accommodation-cost');
        const foodCost = document.getElementById('food-cost');
        const activitiesCost = document.getElementById('activities-cost');
        const days = document.getElementById('days');
        const totalCost = document.getElementById('total-cost');
        const transportationDisplay = document.getElementById('transportation-display');
        const accommodationDisplay = document.getElementById('accommodation-display');
        const foodDisplay = document.getElementById('food-display');
        const activitiesDisplay = document.getElementById('activities-display');
        const ctx = document.getElementById('myChart').getContext('2d');
        let chart;

        calculateBudget.addEventListener('click', () => {
            const transportation = parseInt(transportationCost.value);
            const accommodation = parseInt(accommodationCost.value);
            const food = parseInt(foodCost.value);
            const activities = parseInt(activitiesCost.value);
            const total = transportation + accommodation + food + activities;
            const dailyCost = total / parseInt(days.value);

            totalCost.textContent = `Total Cost: $${total}`;
            transportationDisplay.textContent = `Transportation: $${transportation}`;
            accommodationDisplay.textContent = `Accommodation: $${accommodation}`;
            foodDisplay.textContent = `Food: $${food}`;
            activitiesDisplay.textContent = `Activities: $${activities}`;

            if (chart) {
                chart.destroy();
            }

            chart = new Chart(ctx, {
                type: 'pie',
                data: {
                    labels: ['Transportation', 'Accommodation', 'Food', 'Activities'],
                    datasets: [{
                        label: 'Budget Breakdown',
                        data: [transportation, accommodation, food, activities],
                        backgroundColor: [
                            'rgba(255, 99, 132, 0.2)',
                            'rgba(54, 162, 235, 0.2)',
                            'rgba(255, 206, 86, 0.2)',
                            'rgba(75, 192, 192, 0.2)'
                        ],
                        borderColor: [
                            'rgba(255, 99, 132, 1)',
                            'rgba(54, 162, 235, 1)',
                            'rgba(255, 206, 86, 1)',
                            'rgba(75, 192, 192, 1)'
                        ],
                        borderWidth: 1
                    }]
                },
                options: {
                    animation: {
                        duration: 2000
                    }
                }
            });
            showPage('summary');
        });
    </script>
</body>
</html>
