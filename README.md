index.html <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>GameVault - Play Free Games</title>

    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: Arial, Helvetica, sans-serif;
            background: #070712;
            color: white;
        }

        /* NAVIGATION */
        nav {
            height: 70px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 0 6%;
            background: rgba(10, 10, 22, 0.95);
            border-bottom: 1px solid #202033;
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .logo {
            font-size: 25px;
            font-weight: bold;
            color: #7c5cff;
        }

        nav a {
            color: #bbb;
            text-decoration: none;
            margin-left: 25px;
            transition: 0.2s;
        }

        nav a:hover {
            color: white;
        }

        /* HERO */
        .hero {
            min-height: 430px;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            padding: 60px 20px;

            background:
                radial-gradient(circle at 20% 50%, #25205a 0%, transparent 35%),
                radial-gradient(circle at 80% 50%, #351449 0%, transparent 35%),
                linear-gradient(135deg, #080812, #111126, #080812);
        }

        .hero-content {
            max-width: 800px;
        }

        .hero h1 {
            font-size: clamp(45px, 8vw, 85px);
            margin-bottom: 15px;
            background: linear-gradient(90deg, #8b6cff, #d56cff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .hero p {
            color: #aaa;
            font-size: 20px;
            margin-bottom: 30px;
        }

        .search {
            width: min(600px, 90%);
            padding: 17px 22px;
            border-radius: 12px;
            border: 1px solid #33334d;
            background: #11111e;
            color: white;
            font-size: 16px;
            outline: none;
        }

        .search:focus {
            border-color: #8066ff;
        }

        /* MAIN */
        main {
            width: 90%;
            max-width: 1250px;
            margin: 50px auto;
        }

        .section-title {
            font-size: 30px;
            margin-bottom: 25px;
        }

        /* CATEGORIES */
        .categories {
            display: flex;
            gap: 10px;
            flex-wrap: wrap;
            margin-bottom: 35px;
        }

        .category {
            border: 1px solid #303047;
            background: #11111d;
            color: #bbb;
            padding: 10px 18px;
            border-radius: 30px;
            cursor: pointer;
            transition: 0.2s;
        }

        .category:hover,
        .category.active {
            background: #765cff;
            color: white;
            border-color: #765cff;
        }

        /* GAME GRID */
        .games {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
            gap: 22px;
        }

        .game-card {
            background: #11111d;
            border: 1px solid #24243a;
            border-radius: 15px;
            overflow: hidden;
            transition: 0.25s;
            cursor: pointer;
        }

        .game-card:hover {
            transform: translateY(-7px);
            border-color: #765cff;
            box-shadow: 0 10px 35px rgba(118, 92, 255, 0.18);
        }

        .game-image {
            height: 145px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 45px;

            background:
                linear-gradient(135deg, #202052, #421c4c);
        }

        .game-info {
            padding: 18px;
        }

        .game-info h3 {
            margin-bottom: 7px;
        }

        .game-info p {
            color: #888;
            font-size: 14px;
        }

        .play-button {
            width: 100%;
            margin-top: 15px;
            padding: 11px;
            border: none;
            border-radius: 8px;
            background: #765cff;
            color: white;
            font-weight: bold;
            cursor: pointer;
        }

        .play-button:hover {
            background: #8b75ff;
        }

        /* FOOTER */
        footer {
            margin-top: 80px;
            padding: 35px;
            text-align: center;
            color: #666;
            border-top: 1px solid #202033;
        }

        /* MOBILE */
        @media (max-width: 600px) {
            nav {
                padding: 0 20px;
            }

            nav a {
                display: none;
            }

            .hero {
                min-height: 400px;
            }

            .games {
                grid-template-columns: repeat(2, 1fr);
                gap: 12px;
            }

            .game-image {
                height: 110px;
            }
        }
    </style>
</head>

<body>

    <!-- NAVIGATION -->
    <nav>
        <div class="logo">🎮 GameVault</div>

        <div>
            <a href="#">Home</a>
            <a href="#games">Games</a>
            <a href="#">About</a>
        </div>
    </nav>


    <!-- HERO -->
    <section class="hero">

        <div class="hero-content">

            <h1>GAMEVAULT</h1>

            <p>
                Discover and play awesome games, all in one place.
            </p>

            <input
                class="search"
                type="text"
                placeholder="Search for a game..."
                id="search"
            >

        </div>

    </section>


    <!-- MAIN CONTENT -->
    <main id="games">

        <h2 class="section-title">Browse Games</h2>


        <!-- CATEGORIES -->
        <div class="categories">

            <button class="category active">All</button>
            <button class="category">Action</button>
            <button class="category">Arcade</button>
            <button class="category">Puzzle</button>
            <button class="category">Racing</button>
            <button class="category">Adventure</button>

        </div>


        <!-- GAME CARDS -->
        <div class="games" id="gameGrid">


            <div class="game-card" data-name="Space Runner">

                <div class="game-image">
                    🚀
                </div>

                <div class="game-info">

                    <h3>Space Runner</h3>

                    <p>Arcade • Action</p>

                    <button
                        class="play-button"
                        onclick="playGame('games/space-runner/')">
                        PLAY
                    </button>

                </div>

            </div>


            <div class="game-card" data-name="Pixel Adventure">

                <div class="game-image">
                    🏰
                </div>

                <div class="game-info">

                    <h3>Pixel Adventure</h3>

                    <p>Adventure</p>

                    <button
                        class="play-button"
                        onclick="playGame('games/pixel-adventure/')">
                        PLAY
                    </button>

                </div>

            </div>


            <div class="game-card" data-name="Speed Racer">

                <div class="game-image">
                    🏎️
                </div>

                <div class="game-info">

                    <h3>Speed Racer</h3>

                    <p>Racing</p>

                    <button
                        class="play-button"
                        onclick="playGame('games/speed-racer/')">
                        PLAY
                    </button>

                </div>

            </div>


            <div class="game-card" data-name="Block Puzzle">

                <div class="game-image">
                    🧩
                </div>

                <div class="game-info">

                    <h3>Block Puzzle</h3>

                    <p>Puzzle</p>

                    <button
                        class="play-button"
                        onclick="playGame('games/block-puzzle/')">
                        PLAY
                    </button>

                </div>

            </div>


        </div>

    </main>


    <!-- FOOTER -->
    <footer>

        © 2026 GameVault • All Rights Reserved

    </footer>


    <!-- JAVASCRIPT -->
    <script>

        function playGame(url) {
            window.location.href = url;
        }


        // GAME SEARCH

        const search = document.getElementById("search");

        const cards = document.querySelectorAll(".game-card");

        search.addEventListener("input", function () {

            const query = search.value.toLowerCase();

            cards.forEach(card => {

                const name =
                    card.dataset.name.toLowerCase();

                if (name.includes(query)) {
                    card.style.display = "";
                } else {
                    card.style.display = "none";
                }

            });

        });


        // CATEGORY BUTTONS

        const categories =
            document.querySelectorAll(".category");

        categories.forEach(button => {

            button.addEventListener("click", () => {

                categories.forEach(b =>
                    b.classList.remove("active")
                );

                button.classList.add("active");

            });

        });

    </script>

</body>
</html>
