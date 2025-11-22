# First-game
PATH OF THE NATION: THE COMPLETE GAME
Iraq Political RPG (1950-1958)

=====================================
INSTRUCTIONS FOR GITHUB PAGES:
=====================================

1. Go to github.com and create account (free)
2. Click "New Repository" (green button)
3. Name: "path-of-the-nation" 
4. Check "Public" and "Add README"
5. Click "Create Repository"
6. Click "Add file" → "Create new file"
7. Name it: "index.html"
8. Copy ALL code below and paste
9. Click "Commit changes"
10. Go to Settings → Pages → Select "main branch" → Save
11. Wait 2 minutes, your game will be live at: yourusername.github.io/path-of-the-nation

=====================================
COPY EVERYTHING BELOW THIS LINE
=====================================

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Path of the Nation - Iraq 1950</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Georgia', 'Times New Roman', serif;
            background: linear-gradient(135deg, #1a1410 0%, #2d1f17 50%, #1a1410 100%);
            min-height: 100vh;
            color: #f5e6d3;
            line-height: 1.6;
        }
        
        .game-container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 20px;
        }
        
        /* Ornate Header */
        .game-header {
            text-align: center;
            padding: 60px 20px;
            background: linear-gradient(to bottom, rgba(139,69,19,0.3), transparent);
            border-bottom: 3px solid #8b4513;
            margin-bottom: 40px;
        }
        
        .game-title {
            font-size: 64px;
            color: #d4a574;
            text-shadow: 3px 3px 6px rgba(0,0,0,0.8);
            margin-bottom: 15px;
            font-weight: bold;
            letter-spacing: 3px;
        }
        
        .game-subtitle {
            font-size: 28px;
            color: #c9a76a;
            font-style: italic;
            margin-bottom: 10px;
        }
        
        .game-description {
            font-size: 17px;
            color: #b8956f;
            max-width: 800px;
            margin: 20px auto;
            line-height: 1.8;
        }
        
        /* Character Selection */
        .char-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 40px;
            margin: 50px 0;
        }
        
        .char-card {
            background: linear-gradient(to bottom, #2a1f17, #1f1610);
            border: 3px solid #8b4513;
            border-radius: 15px;
            overflow: hidden;
            cursor: pointer;
            transition: all 0.4s ease;
            box-shadow: 0 10px 30px rgba(0,0,0,0.5);
        }
        
        .char-card:hover {
            transform: translateY(-10px) scale(1.02);
            border-color: #d4a574;
            box-shadow: 0 15px 40px rgba(212,165,116,0.3);
        }
        
        .char-header {
            background: linear-gradient(135deg, #8b4513, #654321);
            padding: 40px 30px;
            text-align: center;
            border-bottom: 2px solid #d4a574;
        }
        
        .char-icon {
            font-size: 100px;
            margin-bottom: 20px;
            filter: drop-shadow(3px 3px 6px rgba(0,0,0,0.8));
        }
        
        .char-name {
            font-size: 32px;
            color: #f5e6d3;
            margin-bottom: 10px;
            font-weight: bold;
        }
        
        .char-tagline {
            font-size: 16px;
            color: #d4a574;
            font-style: italic;
        }
        
        .char-body {
            padding: 35px;
        }
        
        .char-description {
            font-size: 16px;
            color: #c9a76a;
            margin-bottom: 25px;
            line-height: 1.8;
        }
        
        .char-traits {
            background: rgba(139,69,19,0.2);
            padding: 20px;
            border-radius: 10px;
            border: 1px solid #8b4513;
            margin-bottom: 25px;
        }
        
        .char-traits h4 {
            color: #d4a574;
            margin-bottom: 15px;
            font-size: 14px;
            text-transform: uppercase;
            letter-spacing: 2px;
        }
        
        .trait-item {
            display: flex;
            justify-content: space-between;
            margin-bottom: 8px;
            font-size: 14px;
            color: #b8956f;
        }
        
        .trait-value {
            color: #d4a574;
            font-weight: bold;
        }
        
        .char-button {
            width: 100%;
            padding: 18px;
            background: linear-gradient(135deg, #8b4513, #654321);
            color: #f5e6d3;
            border: 2px solid #d4a574;
            border-radius: 10px;
            font-size: 18px;
            font-weight: bold;
            cursor: pointer;
            text-transform: uppercase;
            letter-spacing: 2px;
            transition: all 0.3s ease;
        }
        
        .char-button:hover {
            background: linear-gradient(135deg, #654321, #4a3218);
            border-color: #f5e6d3;
            transform: scale(1.02);
        }
        
        /* Story Screen */
        .story-screen {
            display: none;
        }
        
        .story-nav {
            background: linear-gradient(to right, #8b4513, #654321);
            padding: 25px;
            border-radius: 12px;
            margin-bottom: 30px;
            border: 2px solid #d4a574;
            box-shadow: 0 5px 20px rgba(0,0,0,0.5);
        }
        
        .story-nav h2 {
            font-size: 28px;
            color: #f5e6d3;
            margin-bottom: 15px;
        }
        
        .story-meta {
            display: flex;
            justify-content: space-between;
            flex-wrap: wrap;
            gap: 20px;
            font-size: 15px;
            color: #d4a574;
        }
        
        .story-layout {
            display: grid;
            grid-template-columns: 2fr 1fr;
            gap: 30px;
        }
        
        .story-main {
            background: linear-gradient(to bottom, #2a1f17, #1f1610);
            padding: 45px;
            border-radius: 15px;
            border: 2px solid #8b4513;
            box-shadow: 0 10px 30px rgba(0,0,0,0.5);
        }
        
        .story-title {
            font-size: 36px;
            color: #d4a574;
            margin-bottom: 30px;
            border-bottom: 3px solid #8b4513;
            padding-bottom: 15px;
        }
        
        .story-content {
            font-size: 18px;
            color: #c9a76a;
            line-height: 2;
            margin-bottom: 40px;
        }
        
        .story-content p {
            margin-bottom: 25px;
            text-align: justify;
        }
        
        .story-content em {
            color: #d4a574;
            font-style: italic;
        }
        
        .choices-header {
            font-size: 24px;
            color: #d4a574;
            margin-bottom: 20px;
            font-style: italic;
            text-align: center;
        }
        
        .choice-btn {
            width: 100%;
            padding: 25px;
            margin-bottom: 15px;
            background: linear-gradient(to right, rgba(139,69,19,0.3), rgba(101,67,33,0.3));
            border: 2px solid #8b4513;
            border-radius: 12px;
            color: #c9a76a;
            font-size: 17px;
            text-align: left;
            cursor: pointer;
            transition: all 0.3s ease;
            line-height: 1.7;
            position: relative;
            padding-left: 50px;
        }
        
        .choice-btn::before {
            content: '→';
            position: absolute;
            left: 20px;
            font-size: 24px;
            color: #d4a574;
            font-weight: bold;
        }
        
        .choice-btn:hover {
            background: linear-gradient(to right, rgba(139,69,19,0.5), rgba(101,67,33,0.5));
            border-color: #d4a574;
            transform: translateX(10px);
            color: #f5e6d3;
        }
        
        .choice-impact {
            font-size: 13px;
            color: #8b6914;
            margin-top: 8px;
            font-style: italic;
        }
        
        /* Sidebar */
        .story-sidebar {
            display: flex;
            flex-direction: column;
            gap: 25px;
        }
        
        .sidebar-panel {
            background: linear-gradient(to bottom, #2a1f17, #1f1610);
            padding: 30px;
            border-radius: 15px;
            border: 2px solid #8b4513;
            box-shadow: 0 5px 20px rgba(0,0,0,0.5);
        }
        
        .sidebar-title {
            font-size: 22px;
            color: #d4a574;
            margin-bottom: 20px;
            text-transform: uppercase;
            letter-spacing: 2px;
            text-align: center;
            border-bottom: 2px solid #8b4513;
            padding-bottom: 10px;
        }
        
        .stat-item {
            margin-bottom: 18px;
        }
        
        .stat-label {
            display: flex;
            justify-content: space-between;
            margin-bottom: 8px;
            font-size: 15px;
        }
        
        .stat-name {
            color: #b8956f;
            text-transform: capitalize;
        }
        
        .stat-value {
            color: #d4a574;
            font-weight: bold;
            font-size: 16px;
        }
        
        .stat-bar {
            height: 12px;
            background: rgba(139,69,19,0.3);
            border-radius: 6px;
            overflow: hidden;
            border: 1px solid #654321;
        }
        
        .stat-fill {
            height: 100%;
            background: linear-gradient(to right, #8b4513, #d4a574, #8b4513);
            border-radius: 6px;
            transition: width 0.8s ease;
            box-shadow: 0 0 10px rgba(212,165,116,0.5);
        }
        
        .family-info {
            color: #b8956f;
            font-size: 14px;
            line-height: 1.8;
        }
        
        .family-member {
            padding: 12px;
            background: rgba(139,69,19,0.2);
            border-radius: 8px;
            margin-bottom: 10px;
            border-left: 3px solid #8b4513;
        }
        
        /* Continue Button */
        .continue-btn {
            width: 100%;
            padding: 20px;
            background: linear-gradient(135deg, #8b4513, #654321);
            color: #f5e6d3;
            border: 2px solid #d4a574;
            border-radius: 12px;
            font-size: 20px;
            font-weight: bold;
            cursor: pointer;
            text-transform: uppercase;
            letter-spacing: 2px;
            margin-top: 30px;
            transition: all 0.3s ease;
        }
        
        .continue-btn:hover {
            background: linear-gradient(135deg, #654321, #4a3218);
            transform: scale(1.02);
        }
        
        /* Responsive */
        @media (max-width: 1024px) {
            .story-layout {
                grid-template-columns: 1fr;
            }
            .char-grid {
                grid-template-columns: 1fr;
            }
        }
        
        @media (max-width: 768px) {
            .game-title {
                font-size: 42px;
            }
            .story-main {
                padding: 25px;
            }
            .story-title {
                font-size: 28px;
            }
        }
        
        /* Animations */
        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        .fade-in {
            animation: fadeIn 0.6s ease;
        }
        
        /* End Screen */
        .end-screen {
            display: none;
            text-align: center;
            padding: 60px 20px;
        }
        
        .end-box {
            max-width: 800px;
            margin: 0 auto;
            background: linear-gradient(to bottom, #2a1f17, #1f1610);
            padding: 60px 40px;
            border-radius: 20px;
            border: 3px solid #8b4513;
            box-shadow: 0 15px 50px rgba(0,0,0,0.8);
        }
        
        .end-box h2 {
            font-size: 48px;
            color: #d4a574;
            margin-bottom: 30px;
        }
        
        .end-description {
            font-size: 19px;
            color: #c9a76a;
            margin-bottom: 40px;
            line-height: 1.9;
        }
        
        .final-stats-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 20px;
            margin-bottom: 40px;
        }
        
        .final-stat {
            background: rgba(139,69,19,0.3);
            padding: 20px;
            border-radius: 10px;
            border: 1px solid #8b4513;
        }
        
        .final-stat-name {
            color: #b8956f;
            font-size: 14px;
            margin-bottom: 8px;
            text-transform: uppercase;
        }
        
        .final-stat-value {
            color: #d4a574;
            font-size: 32px;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <div class="game-container">
        <!-- Character Selection -->
        <div id="charSelect">
            <div class="game-header fade-in">
                <h1 class="game-title">PATH OF THE NATION</h1>
                <p class="game-subtitle">Iraq, 1950 - 1958</p>
                <p class="game-description">
                    Three lives. Three destinies. One nation on the brink of revolution.
                    From the palaces of Baghdad to the fields of Najaf, your choices will shape not only your life,
                    but the future of Iraq itself. Navigate family, faith, politics, and power in the final years 
                    of the monarchy. The revolution is coming. Will you rise with it, or fall beneath it?
                </p>
            </div>
            
            <div class="char-grid">
                <div class="char-card fade-in" onclick="selectCharacter('elite')" style="animation-delay: 0.1s">
                    <div class="char-header">
                        <div class="char-icon">🏛️</div>
                        <h3 class="char-name">The Elite</h3>
                        <p class="char-tagline">"Power is inherited, but wisdom must be earned"</p>
                    </div>
                    <div class="char-body">
                        <p class="char-description">
                            Born into Baghdad's aristocracy, you are the heir to a merchant dynasty with ties to the Hashemite court.
                            Your family's wealth flows from vast agricultural estates, and your father sits on government advisory councils.
                            You attend the finest schools, speak English fluently, and move effortlessly through palaces and embassies.
                            But the revolutionary winds are blowing, and the old order you represent may soon be swept away.
                        </p>
                        <div class="char-traits">
                            <h4>Starting Attributes</h4>
                            <div class="trait-item"><span>Influence</span><span class="trait-value">Very High</span></div>
                            <div class="trait-item"><span>Wealth</span><span class="trait-value">Exceptional</span></div>
                            <div class="trait-item"><span>Education</span><span class="trait-value">Elite</span></div>
                            <div class="trait-item"><span>Popular Support</span><span class="trait-value">Very Low</span></div>
                            <div class="trait-item"><span>Religious Authority</span><span class="trait-value">Moderate</span></div>
                        </div>
                        <button class="char-button">Begin Your Journey</button>
                    </div>
                </div>
                
                <div class="char-card fade-in" onclick="selectCharacter('middle')" style="animation-delay: 0.2s">
                    <div class="char-header">
                        <div class="char-icon">📚</div>
                        <h3 class="char-name">The Scholar</h3>
                        <p class="char-tagline">"Knowledge is the bridge between classes"</p>
                    </div>
                    <div class="char-body">
                        <p class="char-description">
                            Your father is a government schoolteacher in Baghdad's al-Rusafa district, respected but never wealthy.
                            You understand both the aspirations of ordinary Iraqis and the machinery of the state. Education is your 
                            family's religion, and you've seen firsthand how knowledge can elevate or exclude. You walk between worlds—
                            too educated for the masses, too poor for the elite. Perhaps that perspective will be your greatest asset.
                        </p>
                        <div class="char-traits">
                            <h4>Starting Attributes</h4>
                            <div class="trait-item"><span>Influence</span><span class="trait-value">Moderate</span></div>
                            <div class="trait-item"><span>Wealth</span><span class="trait-value">Modest</span></div>
                            <div class="trait-item"><span>Education</span><span class="trait-value">High</span></div>
                            <div class="trait-item"><span>Popular Support</span><span class="trait-value">Good</span></div>
                            <div class="trait-item"><span>Religious Authority</span><span class="trait-value">Good</span></div>
                        </div>
                        <button class="char-button">Begin Your Journey</button>
                    </div>
                </div>
                
                <div class="char-card fade-in" onclick="selectCharacter('lower')" style="animation-delay: 0.3s">
                    <div class="char-header">
                        <div class="char-icon">🌾</div>
                        <h3 class="char-name">The Farmer</h3>
                        <p class="char-tagline">"From the soil of suffering grows revolution"</p>
                    </div>
                    <div class="char-body">
                        <p class="char-description">
                            You were born in a mud-brick house near Najaf, where your father works land he'll never own. You've known 
                            hunger, seen your family humiliated by landlords' agents, and learned that justice exists only for the wealthy.
                            But you also possess something the elite cannot buy: authentic connection to Iraq's suffering masses, tribal 
                            networks that span the countryside, and a burning desire to overturn an unjust order. The revolution will need 
                            leaders who understand the people. You are one of them.
                        </p>
                        <div class="char-traits">
                            <h4>Starting Attributes</h4>
                            <div class="trait-item"><span>Influence</span><span class="trait-value">Very Low</span></div>
                            <div class="trait-item"><span>Wealth</span><span class="trait-value">Impoverished</span></div>
                            <div class="trait-item"><span>Education</span><span class="trait-value">Basic</span></div>
        
