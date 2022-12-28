<template>
    <div class="container" id="menu">
        <h1 class="center">Menü</h1>
        <table class="menu-table">
            <tr>
                <th>Étel</th>
                <th>Ár</th>
                <th>Ország</th>
            </tr>
            <tr>
                <td>Hamburger</td>
                <td>1500 Ft</td>
                <td>USA</td>
            </tr>
            <tr>
                <td>Pizza</td>
                <td>3000 Ft</td>
                <td>Olaszország</td>
            </tr>
            <tr>
                <td>Kebab</td>
                <td>1500 Ft</td>
                <td>Törökország</td>
            </tr>
            <tr>
                <td>Kebab tál</td>
                <td>2500 Ft</td>
                <td>Törökország</td>
            </tr>
            <tr>
                <td>Gyros pitában</td>
                <td>1500 Ft</td>
                <td>Görögország</td>
            </tr>
        </table>
    </div>
</template>

<style>
#menu {
    border-bottom: 5px dashed black;
}

.menu-table {
    width: 100%;
    border-collapse: collapse;
    background-color: var(--tertiaryColor);
}

.menu-table th,
.menu-table td {
    text-align: left;
    border: 1px dashed black;
    padding: 5px;
}

.menu-table th {
    background-color: var(--mainColor);
    font-size: 1.5em;
}

.menu-table tr:hover {
    background-color: var(--secondaryColor);
}
</style>