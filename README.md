/photography-site
│── index.html       (主页)
│── style.css        (样式文件)
│── script.js        (交互逻辑)
│── images/          (存放照片)
<!DOCTYPE html>
<html lang="zh">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>摄影作品集</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header>
        <h1>我的摄影作品</h1>
        <nav>
            <a href="#gallery">作品集</a>
            <a href="#about">关于</a>
            <a href="#contact">联系</a>
        </nav>
    </header>

    <section id="gallery" class="masonry-grid">
        <!-- 这里通过JS动态加载图片 -->
    </section>

    <section id="about">
        <h2>关于我</h2>
        <p>这里是关于你的摄影介绍，可以写你的风格、经历等。</p>
    </section>

    <section id="contact">
        <h2>联系我</h2>
        <form id="contact-form">
            <input type="text" placeholder="你的姓名" required>
            <input type="email" placeholder="你的邮箱" required>
            <textarea placeholder="你的留言"></textarea>
            <button type="submit">发送</button>
        </form>
    </section>

    <footer>
        <p>© 2025 我的摄影网站 | <a href="#">Instagram</a> | <a href="#">Twitter</a></p>
    </footer>

    <script src="script.js"></script>
</body>
</html>
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    background: #121212;
    color: white;
    text-align: center;
}

header {
    background: #222;
    padding: 10px;
}

nav a {
    color: white;
    margin: 0 15px;
    text-decoration: none;
}

.masonry-grid {
    column-count: 3;
    column-gap: 10px;
    padding: 20px;
}

.masonry-grid img {
    width: 100%;
    margin-bottom: 10px;
    border-radius: 5px;
    transition: transform 0.3s ease-in-out;
}

.masonry-grid img:hover {
    transform: scale(1.05);
}

#contact-form input, #contact-form textarea {
    width: 80%;
    margin: 10px 0;
    padding: 10px;
}

#contact-form button {
    padding: 10px 20px;
    background: #555;
    color: white;
    border: none;
    cursor: pointer;
}
document.addEventListener("DOMContentLoaded", function () {
    const gallery = document.getElementById("gallery");
    
    const images = [
        "images/photo1.jpg",
        "images/photo2.jpg",
        "images/photo3.jpg",
        "images/photo4.jpg"
    ];

    images.forEach(src => {
        let img = document.createElement("img");
        img.src = src;
        img.alt = "摄影作品";
        gallery.appendChild(img);
    });
});
