<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kapruk Marketplace | Buy & Sell Online</title>
    <style>
        :root {
            --primary: #1e3a8a;
            --primary-hover: #1d4ed8;
            --accent: #f59e0b;
            --accent-hover: #d97706;
            --bg: #f8fafc;
            --card-bg: #ffffff;
            --text-main: #0f172a;
            --text-muted: #64748b;
            --border: #e2e8f0;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: var(--bg);
            color: var(--text-main);
            line-height: 1.6;
        }

        /* Header & Navigation */
        header {
            background-color: var(--primary);
            color: white;
            position: sticky;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem 2rem;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: bold;
            color: #ffffff;
            text-decoration: none;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .logo span {
            color: var(--accent);
        }

        .search-bar {
            flex: 0 1 500px;
            display: flex;
        }

        .search-bar input {
            width: 100%;
            padding: 0.6rem 1rem;
            border: none;
            border-radius: 6px 0 0 6px;
            outline: none;
            font-size: 0.95rem;
        }

        .search-bar button {
            background-color: var(--accent);
            color: white;
            border: none;
            padding: 0 1.5rem;
            border-radius: 0 6px 6px 0;
            cursor: pointer;
            font-weight: bold;
            transition: background 0.2s;
        }

        .search-bar button:hover {
            background-color: var(--accent-hover);
        }

        /* Hero Banner */
        .hero {
            background: linear-gradient(135deg, #1e3a8a 0%, #0f172a 100%);
            color: white;
            text-align: center;
            padding: 4rem 2rem;
        }

        .hero h1 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }

        .hero p {
            font-size: 1.2rem;
            color: #94a3b8;
            max-width: 600px;
            margin: 0 auto 2rem auto;
        }

        /* Main Layout */
        .main-container {
            max-width: 1200px;
            margin: 2rem auto;
            padding: 0 2rem;
            display: grid;
            grid-template-columns: 1fr;
            gap: 2.5rem;
        }

        @media (min-width: 900px) {
            .main-container {
                grid-template-columns: 2fr 1fr;
            }
        }

        /* Product Grid Section */
        .section-title {
            font-size: 1.5rem;
            margin-bottom: 1.5rem;
            position: relative;
            padding-bottom: 0.5rem;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 50px;
            height: 3px;
            background-color: var(--accent);
        }

        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(240px, 1fr));
            gap: 1.5rem;
        }

        .card {
            background: var(--card-bg);
            border: 1px solid var(--border);
            border-radius: 12px;
            overflow: hidden;
            transition: transform 0.2s, box-shadow 0.2s;
        }

        .card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0,0,0,0.05);
        }

        .card-img {
            width: 100%;
            height: 180px;
            background-color: #e2e8f0;
            object-fit: cover;
        }

        .card-body {
            padding: 1.25rem;
        }

        .card-tag {
            display: inline-block;
            background: #eff6ff;
            color: var(--primary);
            font-size: 0.75rem;
            font-weight: bold;
            padding: 0.25rem 0.6rem;
            border-radius: 50px;
            margin-bottom: 0.5rem;
        }

        .card-title {
            font-size: 1.1rem;
            margin-bottom: 0.5rem;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }

        .card-price {
            font-size: 1.3rem;
            font-weight: bold;
            color: var(--primary);
            margin-bottom: 1rem;
        }

        .btn {
            display: block;
            width: 100%;
            text-align: center;
            background-color: var(--primary);
            color: white;
            padding: 0.6rem;
            border: none;
            border-radius: 6px;
            font-weight: 600;
            cursor: pointer;
            text-decoration: none;
            transition: background 0.2s;
        }

        .btn:hover {
            background-color: var(--primary-hover);
        }

        /* Sidebar / Upload Form */
        .sidebar-panel {
            background: var(--card-bg);
            border: 1px solid var(--border);
            border-radius: 12px;
            padding: 1.5rem;
            height: fit-content;
            box-shadow: 0 4px 6px rgba(0,0,0,0.02);
        }

        .form-group {
            margin-bottom: 1.25rem;
        }

        .form-group label {
            display: block;
            font-weight: 600;
            margin-bottom: 0.5rem;
            font-size: 0.9rem;
        }

        .form-group input, .form-group select, .form-group textarea {
            width: 100%;
            padding: 0.65rem;
            border: 1px solid var(--border);
            border-radius: 6px;
            outline: none;
            font-size: 0.95rem;
            background-color: #fafafa;
        }

        .form-group input:focus, .form-group select:focus, .form-group textarea:focus {
            border-color: var(--primary);
            background-color: #fff;
        }

        .btn-accent {
            background-color: var(--accent);
        }

        .btn-accent:hover {
            background-color: var(--accent-hover);
        }

        /* Footer */
        footer {
            background-color: #0f172a;
            color: #94a3b8;
            text-align: center;
            padding: 2rem;
            margin-top: 4rem;
            border-top: 1px solid #1e293b;
        }
    </style>
</head>
<body>

    <header>
        <div class="nav-container">
            <a href="#" class="logo">Kapruk<span>.com</span></a>
            <div class="search-bar">
                <input type="text" placeholder="Search for items, electronics, cars...">
                <button>Search</button>
            </div>
        </div>
    </header>

    <section class="hero">
        <h1>Welcome to Kapruk Marketplace</h1>
        <p>The safest and fastest online destination to buy and sell premium items instantly.</p>
    </section>

    <div class="main-container">
        
        <main>
            <h2 class="section-title">Latest Listings</h2>
            <div class="grid">
                
                <div class="card">
                    <img src="https://images.unsplash.com/photo-1511707171634-5f897ff02aa9?w=400&auto=format&fit=crop&q=60" alt="Smartphone" class="card-img">
                    <div class="card-body">
                        <span class="card-tag">Electronics</span>
                        <h3 class="card-title">Flagship Smartphone</h3>
                        <p class="card-price">$699</p>
                        <button class="btn">View Details</button>
                    </div>
                </div>

                <div class="card">
                    <img src="https://images.unsplash.com/photo-1516035069371-29a1b244cc32?w=400&auto=format&fit=crop&q=60" alt="Camera" class="card-img">
                    <div class="card-body">
                        <span class="card-tag">Photography</span>
                        <h3 class="card-title">Professional DSLR Camera</h3>
                        <p class="card-price">$1,250</p>
                        <button class="btn">View Details</button>
                    </div>
                </div>

                <div class="card">
                    <img src="https://images.unsplash.com/photo-1542291026-7eec264c27ff?w=400&auto=format&fit=crop&q=60" alt="Shoes" class="card-img">
                    <div class="card-body">
                        <span class="card-tag">Fashion</span>
                        <h3 class="card-title">Premium Running Shoes</h3>
                        <p class="card-price">$120</p>
                        <button class="btn">View Details</button>
                    </div>
                </div>

            </div>
        </main>

        <aside>
            <div class="sidebar-panel">
                <h2 class="section-title" style="margin-bottom:1rem;">Post New Item</h2>
                <form onsubmit="event.preventDefault(); alert('Item submitted for review!');">
                    <div class="form-group">
                        <label for="title">Item Title</label>
                        <input type="text" id="title" placeholder="e.g., iPhone 15 Pro Max" required>
                    </div>
                    <div class="form-group">
                        <label for="category">Category</label>
                        <select id="category">
                            <option>Electronics</option>
                            <option>Fashion</option>
                            <option>Vehicles</option>
                            <option>Property</option>
                        </select>
                    </div>
                    <div class="form-group">
                        <label for="price">Price ($)</label>
                        <input type="number" id="price" placeholder="Enter amount" required>
                    </div>
                    <div class="form-group">
                        <label for="image">Upload Product Image</label>
                        <input type="file" id="image" accept="image/*">
                    </div>
                    <button type="submit" class="btn btn-accent">List Item Now</button>
                </form>
            </div>
        </aside>

    </div>

    <footer>
        <p>&copy; 2026 Kapruk Marketplace. All rights reserved.</p>
    </footer>

</body>
</html>
