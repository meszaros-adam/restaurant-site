<template>
    <ul class="nav">
        <li>
            <a href="">Menü</a>
        </li>
        <li>
            <a href="">Elérhetőség</a>
        </li>
        <li>
            <a href="">Nyitvatartás</a>
        </li>
    </ul>
</template>

<style>
.nav {
    display: flex;
    list-style: none;
    justify-content: center;
    padding: 10px 20px;
    margin-top: 0;
    background-color: #84757a;
    border-color: black;
    border-style: dashed;
    border-width: 2px 0px;
}

.nav li {
    margin: 0 20px;
}

.nav a {
    color: black;
    text-decoration: none;
}

.nav a:hover {
    text-decoration: underline;
    font-weight: 900;
}
</style>