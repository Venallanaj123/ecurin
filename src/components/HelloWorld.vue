<template>
    <nav>
        <div class="navbar">
            <i class="bx bx-menu"></i>
            <div class="logo"><a href="#">CodingLab</a></div>
            <div class="nav-links">
                <div class="sidebar-logo">
                    <span class="logo-name">CodingLab</span>
                    <i class="bx bx-x"></i>
                </div>
                <ul class="links">
                    <li><a href="">HTML & CSS</a>
                        <i class='bx bxs-chevron-down htmlcss-arrow arrow  '></i>
                        <ul class="htmlCss-sub-menu sub-menu">
                            <li><a href="#">Web Design</a></li>
                            <li><a href="#">Login Forms</a></li>
                            <li><a href="#">Card Design</a></li>
                            <li class="more">
                                <span> <a href="#">More</a> <i class='bx bxs-chevron-right arrow more-arrow'></i></span>

                                <ul class="more-sub-menu sub-menu">
                                    <li><a href="#">Neumorphism</a></li>
                                    <li><a href="#">Pre-loader</a></li>
                                    <li><a href="#">Glassmorphism</a></li>
                                </ul>
                            </li>

                        </ul>

                    </li>
                </ul>
            </div>
        </div>
    </nav>
</template>

<script>
export default {
    name: 'HelloWorld',
    props: {
        msg: String
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
    margin: 40px 0 0;
}

ul {
    list-style-type: none;
    padding: 0;
}

li {
    display: inline-block;
    margin: 0 10px;
}

a {
    color: green;
}
</style>
