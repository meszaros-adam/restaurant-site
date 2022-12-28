<template>
    <div id="opening">
        <h1 class="center">Nyitvatartás</h1>
        <div class="flex">
            <div>
                <table>
                    <tr>
                        <th>Nap</th>
                        <th>Nyitvatartás</th>
                    </tr>
                    <tr>
                        <td>Hétfő</td>
                        <td>08-20</td>
                    </tr>
                    <tr>
                        <td>Kedd</td>
                        <td>08-20</td>
                    </tr>
                    <tr>
                        <td>Szerda</td>
                        <td>08-20</td>
                    </tr>
                    <tr>
                        <td>Csütörtök</td>
                        <td>08-20</td>
                    </tr>
                    <tr>
                        <td>Péntek</td>
                        <td>08-20</td>
                    </tr>
                    <tr>
                        <td>Szombat</td>
                        <td>08-20</td>
                    </tr>
                    <tr>
                        <td>Vasárnap</td>
                        <td>08-20</td>
                    </tr>
                </table>
            </div>
            <div>
                <img src="../assets/images/door_5481543.jpg" alt="">
            </div>
        </div>

    </div>

</template>

<style >
#opening th {
    text-align: start;
}

#opening {
    background-color: var(--mainColor);
    padding: 3rem;
}

#opening .flex {
    display: flex;
    justify-content: space-around;
    align-items: center;
}

#opening img {
    border-radius: var(--borderRadius);
    max-width: 100%;
    height: auto;
}

#opening table {
    border: dashed 2px black;
    padding: 2rem;
    border-radius: var(--borderRadius);
    font-size: xx-large;
}

@media screen and (max-width: 992px) {
    #opening .flex {
        flex-direction: column;
    }

    #opening img {
        box-sizing: border-box;
        padding: 1rem;
    }
}
</style>
