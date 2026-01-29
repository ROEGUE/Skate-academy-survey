# Skate Academy Survey

This repository holds the Skate Academy Swansea market research survey. Below is the full HTML for the market research survey page (file: `market-research-survey.html`).

```html
<!DOCTYPE html>

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Skate Academy Swansea - Market Research Survey</title>
    <link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Anton&family=Archivo:wght@400;600&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

    :root {
        --primary: #4A90A4;
        --secondary: #F4E5C2;
        --accent: #E8B86D;
        --dark: #3D5A6C;
        --light: #F9F7F0;
        --cream: #FAF7F0;
        --sand: #D4C5A9;
        --sky: #A8C5D1;
    }

    body {
        font-family: 'Archivo', sans-serif;
        background: linear-gradient(135deg, var(--cream) 0%, var(--secondary) 50%, var(--sky) 100%);
        color: var(--dark);
        min-height: 100vh;
        padding: 0;
        position: relative;
        overflow-x: hidden;
    }

    body::before {
        content: '';
        position: fixed;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        background: 
            repeating-linear-gradient(
                45deg,
                transparent,
                transparent 10px,
                rgba(74, 144, 164, 0.02) 10px,
                rgba(74, 144, 164, 0.02) 20px
            );
        pointer-events: none;
        z-index: 1;
    }

    .container {
        max-width: 900px;
        margin: 0 auto;
        padding: 40px 20px;
        position: relative;
        z-index: 2;
    }

    .header {
        text-align: center;
        margin-bottom: 60px;
        position: relative;
    }

    .header::before {
        content: '';
        position: absolute;
        top: -20px;
        left: 50%;
        transform: translateX(-50%);
        width: 100px;
        height: 4px;
        background: linear-gradient(90deg, var(--primary), var(--accent));
    }

    .logo {
        font-family: 'Bebas Neue', sans-serif;
        font-size: 64px;
        letter-spacing: 4px;
        background: linear-gradient(135deg, var(--primary) 0%, var(--dark) 100%);
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        background-clip: text;
        margin-bottom: 10px;
        text-transform: uppercase;
        animation: slideDown 0.8s ease-out;
    }

    @keyframes slideDown {
        from {
            opacity: 0;
            transform: translateY(-30px);
        }
        to {
            opacity: 1;
            transform: translateY(0);
        }
    }

    .subtitle {
        font-size: 20px;
        color: var(--dark);
        font-weight: 600;
        margin-bottom: 20px;
        animation: fadeIn 1s ease-out 0.3s both;
    }

    @keyframes fadeIn {
        from { opacity: 0; }
        to { opacity: 1; }
    }

    .intro {
        background: rgba(255, 255, 255, 0.7);
        backdrop-filter: blur(10px);
        border: 2px solid var(--sand);
        border-radius: 12px;
        padding: 30px;
        margin-bottom: 50px;
        font-size: 16px;
        line-height: 1.6;
        color: var(--dark);
        animation: fadeIn 1s ease-out 0.6s both;
        box-shadow: 0 4px 20px rgba(74, 144, 164, 0.1);
    }

    .form-section {
        background: rgba(255, 255, 255, 0.8);
        backdrop-filter: blur(10px);
        border-left: 4px solid var(--primary);
        border-radius: 8px;
        padding: 40px;
        margin-bottom: 40px;
        animation: slideUp 0.6s ease-out both;
        transition: all 0.3s ease;
        box-shadow: 0 4px 15px rgba(74, 144, 164, 0.15);
    }

    .form-section:hover {
        background: rgba(255, 255, 255, 0.95);
        transform: translateX(5px);
        box-shadow: 0 6px 25px rgba(74, 144, 164, 0.2);
    }

    @keyframes slideUp {
        from {
            opacity: 0;
            transform: translateY(30px);
        }
        to {
            opacity: 1;
            transform: translateY(0);
        }
    }

    .form-section:nth-child(1) { animation-delay: 0.1s; }
    .form-section:nth-child(2) { animation-delay: 0.2s; }
    .form-section:nth-child(3) { animation-delay: 0.3s; }
    .form-section:nth-child(4) { animation-delay: 0.4s; }

    .section-title {
        font-family: 'Anton', sans-serif;
        font-size: 28px;
        color: var(--primary);
        margin-bottom: 30px;
        text-transform: uppercase;
        letter-spacing: 2px;
        position: relative;
        padding-bottom: 15px;
    }

    .section-title::after {
        content: '';
        position: absolute;
        bottom: 0;
        left: 0;
        width: 60px;
        height: 3px;
        background: var(--accent);
    }

    .question {
        margin-bottom: 35px;
    }

    .question-label {
        display: block;
        font-size: 17px;
        font-weight: 600;
        color: var(--dark);
        margin-bottom: 15px;
        line-height: 1.5;
    }

    .question-number {
        display: inline-block;
        background: var(--accent);
        color: white;
        width: 28px;
        height: 28px;
        border-radius: 50%;
        text-align: center;
        line-height: 28px;
        font-size: 14px;
        margin-right: 10px;
        font-weight: bold;
    }

    .options {
        display: flex;
        flex-direction: column;
        gap: 12px;
    }

    .option {
        display: flex;
        align-items: center;
        padding: 15px 20px;
        background: rgba(250, 247, 240, 0.9);
        border: 2px solid var(--sand);
        border-radius: 8px;
        cursor: pointer;
        transition: all 0.3s ease;
        position: relative;
    }

    .option:hover {
        background: rgba(168, 197, 209, 0.2);
        border-color: var(--primary);
        transform: translateX(5px);
    }

    .option input[type="radio"],
    .option input[type="checkbox"] {
        margin-right: 15px;
        width: 20px;
        height: 20px;
        cursor: pointer;
        accent-color: var(--primary);
        pointer-events: auto;
    }

    .option label {
        cursor: pointer;
        flex: 1;
        font-size: 15px;
        color: var(--dark);
        pointer-events: none;
    }

    input[type="text",
    input[type="email",
    input[type="tel",
    textarea] {
        width: 100%;
        padding: 15px 20px;
        background: rgba(250, 247, 240, 0.9);
        border: 2px solid var(--sand);
        border-radius: 8px;
        color: var(--dark);
        font-family: 'Archivo', sans-serif;
        font-size: 15px;
        transition: all 0.3s ease;
    }

    input[type="text"]:focus,
    input[type="email"]:focus,
    input[type="tel"]:focus,
    textarea:focus {
        outline: none;
        border-color: var(--primary);
        background: rgba(255, 255, 255, 0.95);
    }

    textarea {
        min-height: 120px;
        resize: vertical;
    }

    .ranking-inputs {
        display: grid;
        gap: 15px;
    }

    .ranking-item {
        display: flex;
        align-items: center;
        gap: 15px;
        padding: 15px;
        background: rgba(250, 247, 240, 0.9);
        border-radius: 8px;
        border: 2px solid var(--sand);
    }

    .ranking-item input[type="number"] {
        width: 60px;
        padding: 8px;
        text-align: center;
        background: rgba(255, 255, 255, 0.9);
        border: 2px solid var(--sand);
        border-radius: 6px;
        color: var(--dark);
        font-weight: bold;
    }

    .ranking-item label {
        flex: 1;
        color: var(--dark);
    }

    .submit-section {
        background: rgba(232, 184, 109, 0.15);
        backdrop-filter: blur(10px);
        border: 2px solid var(--accent);
        border-radius: 12px;
        padding: 40px;
        text-align: center;
        margin-top: 60px;
        box-shadow: 0 4px 20px rgba(232, 184, 109, 0.2);
    }

    .submit-title {
        font-family: 'Anton', sans-serif;
        font-size: 32px;
        color: var(--dark);
        margin-bottom: 20px;
        text-transform: uppercase;
        letter-spacing: 2px;
    }

    .submit-text {
        color: var(--dark);
        margin-bottom: 30px;
        line-height: 1.6;
    }

    .contact-fields {
        display: grid;
        gap: 20px;
        margin-bottom: 30px;
        text-align: left;
    }

    .contact-fields label {
        display: block;
        color: var(--dark);
        font-weight: 600;
        margin-bottom: 8px;
        font-size: 15px;
    }

    .submit-btn {
        background: linear-gradient(135deg, var(--primary) 0%, var(--accent) 100%);
        color: white;
        border: none;
        padding: 18px 60px;
        font-size: 18px;
        font-weight: bold;
        font-family: 'Anton', sans-serif;
        letter-spacing: 2px;
        text-transform: uppercase;
        border-radius: 50px;
        cursor: pointer;
        transition: all 0.3s ease;
        box-shadow: 0 8px 20px rgba(74, 144, 164, 0.3);
    }

    .submit-btn:hover {
        transform: translateY(-3px);
        box-shadow: 0 12px 30px rgba(74, 144, 164, 0.4);
    }

    .submit-btn:active {
        transform: translateY(-1px);
    }

    .progress-bar {
        position: fixed;
        top: 0;
        left: 0;
        height: 4px;
        background: linear-gradient(90deg, var(--primary), var(--accent));
        width: 0%;
        transition: width 0.3s ease;
        z-index: 1000;
    }

    .success-message {
        display: none;
        background: linear-gradient(135deg, #7FB069 0%, #5A8F5A 100%);
        color: white;
        padding: 30px;
        border-radius: 12px;
        text-align: center;
        margin-top: 40px;
        font-size: 18px;
        animation: slideDown 0.5s ease-out;
        box-shadow: 0 8px 25px rgba(127, 176, 105, 0.3);
    }

    .success-message.show {
        display: block;
    }

    @media (max-width: 768px) {
        .logo {
            font-size: 48px;
        }
        
        .form-section {
            padding: 25px;
        }
        
        .section-title {
            font-size: 24px;
        }
        
        .option {
            padding: 12px 15px;
        }
    }

    .helper-text {
        font-size: 13px;
        color: rgba(61, 90, 108, 0.7);
        margin-top: 8px;
        font-style: italic;
    }
</style>

</head>
<body>
    <div class="progress-bar" id="progressBar"></div>

<div class="container">
    <div class="header">
        <div class="logo">Skate Academy Swansea</div>
        <div class="subtitle">Market Research Survey</div>
    </div>

    <div class="intro">
        Thank you for taking the time to complete this survey. Your responses will help us understand the needs and preferences of potential customers and enable us to create the best possible skateboarding coaching experience in Swansea. This should take approximately 5-7 minutes to complete. All responses are confidential.
    </div>

    <form id="surveyForm">
        <!-- Section 1: About You -->
        <div class="form-section">
            <h2 class="section-title">Section 1: About You</h2>

            <div class="question">
                <label class="question-label">
                    <span class="question-number">1</span>
                    What is your age (or the age of the person who would be taking lessons)?
                </label>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q1" value="under6" id="q1_1">
                        <label for="q1_1">Under 6</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q1" value="6-8" id="q1_2">
                        <label for="q1_2">6-8</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q1" value="9-10" id="q1_3">
                        <label for="q1_3">9-10</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q1" value="11-15" id="q1_4">
                        <label for="q1_4">11-15</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q1" value="16-20" id="q1_5">
                        <label for="q1_5">16-20</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q1" value="21-30" id="q1_6">
                        <label for="q1_6">21-30</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q1" value="31-40" id="q1_7">
                        <label for="q1_7">31-40</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q1" value="41+" id="q1_8">
                        <label for="q1_8">41+</label>
                    </div>
                </div>
            </div>

            <div class="question">
                <label class="question-label">
                    <span class="question-number">2</span>
                    What is your relationship to the potential learner?
                </label>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q2" value="myself" id="q2_1">
                        <label for="q2_1">I would be taking lessons myself</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q2" value="parent" id="q2_2">
                        <label for="q2_2">Parent/Guardian</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q2" value="family" id="q2_3">
                        <label for="q2_3">Other family member</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q2" value="friend" id="q2_4">
                        <label for="q2_4">Friend</label>
                    </div>
                </div>
            </div>

            <div class="question">
                <label class="question-label">
                    <span class="question-number">3</span>
                    What is your postcode or general area within Swansea and surrounding regions?
                </label>
                <input type="text" name="q3" placeholder="e.g., SA1 or Mumbles">
            </div>
        </div>

        <!-- Section 2: Skateboarding Experience & Motivation -->
        <div class="form-section">
            <h2 class="section-title">Section 2: Skateboarding Experience & Motivation</h2>

            <div class="question">
                <label class="question-label">
                    <span class="question-number">4</span>
                    What is your (or your child's) current skateboarding ability level?
                </label>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q4" value="complete_beginner" id="q4_1">
                        <label for="q4_1">Complete beginner (never skateboarded)</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q4" value="beginner" id="q4_2">
                        <label for="q4_2">Beginner (can push and balance, learning basic turns)</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q4" value="intermediate" id="q4_3">
                        <label for="q4_3">Intermediate (working on basic tricks like ollies, kickturns)</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q4" value="advanced" id="q4_4">
                        <label for="q4_4">Advanced (comfortable with multiple tricks, consistent execution)</label>
                    </div>
                </div>
            </div>

            <div class="question">
                <label class="question-label">
                    <span class="question-number">5</span>
                    What are the main reasons for considering skateboarding lessons? (Select all that apply)
                </label>
                <div class="options">
                    <div class="option">
                        <input type="checkbox" name="q5" value="fundamentals" id="q5_1">
                        <label for="q5_1">Learn proper fundamental techniques from the start</label>
                    </div>
                    <div class="option">
                        <input type="checkbox" name="q5" value="confidence" id="q5_2">
                        <label for="q5_2">Build confidence and overcome fear of injury</label>
                    </div>
                    <div class="option">
                        <input type="checkbox" name="q5" value="specific_tricks" id="q5_3">
                        <label for="q5_3">Learn specific tricks or skills</label>
                    </div>
                    <div class="option">
                        <input type="checkbox" name="q5" value="social" id="q5_4">
                        <label for="q5_4">Social activity with friends or peers</label>
                    </div>
                    <div class="option">
                        <input type="checkbox" name="q5" value="fitness" id="q5_5">
                        <label for="q5_5">Physical fitness and outdoor activity</label>
                    </div>
                    <div class="option">
                        <input type="checkbox" name="q5" value="competitive" id="q5_6">
                        <label for="q5_6">Work toward competitive progression</label>
                    </div>
                    <div class="option">
                        <input type="checkbox" name="q5" value="improve_skills" id="q5_7">
                        <label for="q5_7">Improve existing skills with structured guidance</label>
                    </div>
                    <div class="option">
                        <input type="checkbox" name="q5" value="other" id="q5_8">
                        <label for="q5_8">Other</label>
                    </div>
                </div>
                <input type="text" name="q5_other" placeholder="If other, please specify..." style="margin-top: 15px;">
            </div>

            <div class="question">
                <label class="question-label">
                    <span class="question-number">6</span>
                    How important is injury prevention and safety education in your decision to choose a skateboarding coach?
                </label>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q6" value="extremely" id="q6_1">
                        <label for="q6_1">Extremely important</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q6" value="very" id="q6_2">
                        <label for="q6_2">Very important</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q6" value="moderately" id="q6_3">
                        <label for="q6_3">Moderately important</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q6" value="slightly" id="q6_4">
                        <label for="q6_4">Slightly important</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q6" value="not" id="q6_5">
                        <label for="q6_5">Not important</label>
                    </div>
                </div>
            </div>
        </div>

        <!-- Section 3: Lesson Preferences & Logistics -->
        <div class="form-section">
            <h2 class="section-title">Section 3: Lesson Preferences & Logistics</h2>

            <div class="question">
                <label class="question-label">
                    <span class="question-number">7</span>
                    Which lesson format appeals to you most?
                </label>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q7" value="1on1" id="q7_1">
                        <label for="q7_1">1:1 private lessons for intensive, personalized coaching (£25-£45 per hour)</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q7" value="small_group" id="q7_2">
                        <label for="q7_2">Small group lessons with 2-4 friends/family (discounted rate, approximately £15 per person)</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q7" value="large_group" id="q7_3">
                        <label for="q7_3">Larger group lessons with 5-8 participants (social atmosphere)</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q7" value="bundle" id="q7_4">
                        <label for="q7_4">5-lesson bundle package for structured progression over 5 weeks</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q7" value="weekly_club" id="q7_5">
                        <label for="q7_5">Weekly club sessions for advanced skaters (£8 per session)</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q7" value="not_sure" id="q7_6">
                        <label for="q7_6">Not sure yet, would like more information</label>
                    </div>
                </div>
            </div>

            <div class="question">
                <label class="question-label">
                    <span class="question-number">8</span>
                    What lesson location would you prefer?
                </label>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q8" value="outdoor_only" id="q8_1">
                        <label for="q8_1">Outdoor parks only (Victoria Park, Mumbles Skatepark)</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q8" value="indoor_only" id="q8_2">
                        <label for="q8_2">Indoor skatepark only (EXIST Skatepark)</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q8" value="flexible" id="q8_3">
                        <label for="q8_3">Flexible - either indoor or outdoor depending on weather</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q8" value="indoor_preference" id="q8_4">
                        <label for="q8_4">Strong preference for weather-protected indoor facility</label>
                    </div>
                </div>
            </div>

            <div class="question">
                <label class="question-label">
                    <span class="question-number">9</span>
                    What days and times work best for lessons? (Select all that apply)
                </label>
                <div class="options">
                    <div class="option">
                        <input type="checkbox" name="q9" value="weekday_morning" id="q9_1">
                        <label for="q9_1">Weekday mornings (before 12pm)</label>
                    </div>
                    <div class="option">
                        <input type="checkbox" name="q9" value="weekday_afternoon" id="q9_2">
                        <label for="q9_2">Weekday afternoons (12pm-5pm)</label>
                    </div>
                    <div class="option">
                        <input type="checkbox" name="q9" value="weekday_evening" id="q9_3">
                        <label for="q9_3">Weekday evenings (after 5pm)</label>
                    </div>
                    <div class="option">
                        <input type="checkbox" name="q9" value="saturday_morning" id="q9_4">
                        <label for="q9_4">Saturday mornings</label>
                    </div>
                    <div class="option">
                        <input type="checkbox" name="q9" value="saturday_afternoon" id="q9_5">
                        <label for="q9_5">Saturday afternoons/evenings</label>
                    </div>
                    <div class="option">
                        <input type="checkbox" name="q9" value="sunday_morning" id="q9_6">
                        <label for="q9_6">Sunday mornings</label>
                    </div>
                    <div class="option">
                        <input type="checkbox" name="q9" value="sunday_afternoon" id="q9_7">
                        <label for="q9_7">Sunday afternoons/evenings</label>
                    </div>
                    <div class="option">
                        <input type="checkbox" name="q9" value="flexible" id="q9_8">
                        <label for="q9_8">Very flexible - can accommodate most times</label>
                    </div>
                </div>
            </div>
        </div>

        <!-- Section 4: Commitment & Value -->
        <div class="form-section">
            <h2 class="section-title">Section 4: Commitment & Value</h2>

            <div class="question">
                <label class="question-label">
                    <span class="question-number">10</span>
                    How likely would you be to commit to a multi-lesson package (such as our 5-lesson bundle) versus trying a single lesson first?
                </label>
                <div class="options">
                    <div class="option">
                        <input type="radio" name="q10" value="package_immediately" id="q10_1">
                        <label for="q10_1">Very likely to book a package immediately if it offers good value</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q10" value="trial_first" id="q10_2">
                        <label for="q10_2">Prefer one trial lesson first, then would consider a package</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q10" value="2_3_lessons" id="q10_3">
                        <label for="q10_3">Would book 2-3 single lessons before committing to a package</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q10" value="occasional_only" id="q10_4">
                        <label for="q10_4">Only interested in occasional single lessons, not packages</label>
                    </div>
                    <div class="option">
                        <input type="radio" name="q10" value="depends" id="q10_5">
                        <label for="q10_5">Depends on price difference and perceived value</label>
                    </div>
                </div>
            </div>

            <div class="question">
                <label class="question-label">
                    <span class="question-number">11</span>
                    Which factors are most important when choosing a skateboarding coach? (Rank your top 3, with 1 being most important)
                </label>
                <p class="helper-text">Enter numbers 1-3 for your top priorities. Leave others blank.</p>
                <div class="ranking-inputs">
                    <div class="ranking-item">
                        <input type="number" name="q11_qualified" min="1" max="3" placeholder="Rank">
                        <label>Qualified and experienced instructor credentials</label>
                    </div>
                    <div class="ranking-item">
                        <input type="number" name="q11_safety" min="1" max="3" placeholder="Rank">
                        <label>Strong focus on safety and injury prevention</label>
                    </div>
                    <div class="ranking-item">
                        <input type="number" name="q11_scheduling" min="1" max="3" placeholder="Rank">
                        <label>Flexible scheduling and easy booking process</label>
                    </div>
                    <div class="ranking-item">
                        <input type="number" name="q11_location" min="1" max="3" placeholder="Rank">
                        <label>Convenient location close to home</label>
                    </div>
                    <div class="ranking-item">
                        <input type="number" name="q11_pricing" min="1" max="3" placeholder="Rank">
                        <label>Competitive pricing and value for money</label>
                    </div>
                    <div class="ranking-item">
                        <input type="number" name="q11_personalized" min="1" max="3" placeholder="Rank">
                        <label>Personalized attention and customized lesson plans</label>
                    </div>
                    <div class="ranking-item">
                        <input type="number" name="q11_community" min="1" max="3" placeholder="Rank">
                        <label>Positive community atmosphere and social opportunities</label>
                    </div>
                    <div class="ranking-item">
                        <input type="number" name="q11_progression" min="1" max="3" placeholder="Rank">
                        <label>Clear progression tracking and measurable results</label>
                    </div>
                    <div class="ranking-item">
                        <input type="number" name="q11_indoor" min="1" max="3" placeholder="Rank">
                        <label>Availability of indoor facilities for year-round learning</label>
                    </div>
                </div>
            </div>

            <div class="question">
                <label class="question-label">
                    <span class="question-number">12</span>
                    What concerns or barriers, if any, might prevent you from booking skateboarding lessons? (Please be as specific as possible)
                </label>
                <textarea name="q12" placeholder="Share any concerns about cost, time commitment, fear of injury, equipment needs, weather, transportation, etc."></textarea>
            </div>
        </div>

        <!-- Submit Section -->
        <div class="submit-section">
            <div class="submit-title">Thank You!</div>
            <p class="submit-text">
                Your feedback is invaluable in helping us create the best skateboarding coaching experience in Swansea. If you would like to be contacted about lessons or have any questions, please provide your contact information below:
            </p>
            
            <div class="contact-fields">
                <div>
                    <label for="contact_name">Name (optional)</label>
                    <input type="text" id="contact_name" name="contact_name" placeholder="Your name">
                </div>
                <div>
                    <label for="contact_email">Email (optional)</label>
                    <input type="email" id="contact_email" name="contact_email" placeholder="your.email@example.com">
                </div>
                <div>
                    <label for="contact_phone">Phone (optional)</label>
                    <input type="tel" id="contact_phone" name="contact_phone" placeholder="07XXX XXXXXX">
                </div>
            </div>

            <button type="submit" class="submit-btn">Submit Survey</button>
        </div>
    </form>

    <div class="success-message" id="successMessage">
        <h2 style="margin-bottom: 15px; font-size: 28px;">✓ Survey Submitted Successfully!</h2>
        <p>Thank you for your valuable feedback. Your responses have been recorded and will help us create the best possible skateboarding coaching experience.</p>
    </div>
</div>

<script>
    // Progress bar
    window.addEventListener('scroll', function() {
        const windowHeight = window.innerHeight;
        const documentHeight = document.documentElement.scrollHeight - windowHeight;
        const scrollTop = window.pageYOffset || document.documentElement.scrollTop;
        const scrollPercentage = (scrollTop / documentHeight) * 100;
        document.getElementById('progressBar').style.width = scrollPercentage + '%';
    });

    // Form submission
    document.getElementById('surveyForm').addEventListener('submit', function(e) {
        e.preventDefault();
        
        const formData = new FormData(this);
        const data = {};
        
        // Process form data
        for (let [key, value] of formData.entries()) {
            if (key === 'q5' || key === 'q9') {
                // Handle multiple checkboxes
                if (!data[key]) data[key] = [];
                data[key].push(value);
            } else {
                data[key] = value;
            }
        }

        // Create formatted results
        const results = formatResults(data);
        
        // Save to localStorage
        const timestamp = new Date().toISOString();
        const responseId = 'response_' + timestamp;
        localStorage.setItem(responseId, JSON.stringify({ timestamp, data, results }));
        
        // Get all responses
        const allResponses = getAllResponses();
        console.log('All Survey Responses:', allResponses);
        
        // Download as JSON
        downloadResults(allResponses);
        
        // Show success message
        document.getElementById('surveyForm').style.display = 'none';
        document.getElementById('successMessage').classList.add('show');
        
        // Scroll to top
        window.scrollTo({ top: 0, behavior: 'smooth' });
    });

    function formatResults(data) {
        const questionLabels = {
            q1: "Age range",
            q2: "Relationship to learner",
            q3: "Location",
            q4: "Skill level",
            q5: "Reasons for lessons",
            q5_other: "Other reasons",
            q6: "Importance of safety",
            q7: "Preferred lesson format",
            q8: "Location preference",
            q9: "Preferred times",
            q10: "Package commitment likelihood",
            q11_qualified: "Rank: Qualified instructor",
            q11_safety: "Rank: Safety focus",
            q11_scheduling: "Rank: Flexible scheduling",
            q11_location: "Rank: Convenient location",
            q11_pricing: "Rank: Competitive pricing",
            q11_personalized: "Rank: Personalized attention",
            q11_community: "Rank: Community atmosphere",
            q11_progression: "Rank: Progress tracking",
            q11_indoor: "Rank: Indoor facilities",
            q12: "Concerns/barriers",
            contact_name: "Name",
            contact_email: "Email",
            contact_phone: "Phone"
        };

        const formatted = {};
        for (let key in data) {
            if (data[key]) {
                formatted[questionLabels[key] || key] = data[key];
            }
        }
        return formatted;
    }

    function getAllResponses() {
        const responses = [];
        for (let i = 0; i < localStorage.length; i++) {
            const key = localStorage.key(i);
            if (key.startsWith('response_')) {
                const item = JSON.parse(localStorage.getItem(key));
                responses.push(item);
            }
        }
        return responses.sort((a, b) => new Date(b.timestamp) - new Date(a.timestamp));
    }

    function downloadResults(responses) {
        const dataStr = JSON.stringify(responses, null, 2);
        const blob = new Blob([dataStr], { type: 'application/json' });
        const url = URL.createObjectURL(blob);
        const link = document.createElement('a');
        link.href = url;
        link.download = 'SAS_Survey_Responses_' + new Date().toISOString().split('T')[0] + '.json';
        document.body.appendChild(link);
        link.click();
        document.body.removeChild(link);
        URL.revokeObjectURL(url);
    }

    // Fixed checkbox/radio functionality - only respond to direct input clicks
    document.querySelectorAll('.option').forEach(option => {
        const input = option.querySelector('input');
        
        // Only toggle when clicking the option div, not when clicking the input directly
        option.addEventListener('click', function(e) {
            // If the click was directly on the input, let the browser handle it
            if (e.target === input) {
                return;
            }
            
            // Otherwise, toggle the input
            if (input.type === 'radio') {
                input.checked = true;
            } else if (input.type === 'checkbox') {
                input.checked = !input.checked;
            }
        });
    });
</script>

</body>
</html>
````