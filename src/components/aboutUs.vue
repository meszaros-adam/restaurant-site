<template>
    <div id="about-us">
        <div class="container">
            <h1>Rólunk</h1>
            <figure class="chef">
                <img src="../assets/images/chef.jpg" alt="">
                <figcaption>Kiss Pista - Séf</figcaption>
            </figure>
            <p>
                Lorem ipsum dolor, sit amet consectetur adipisicing elit. Necessitatibus optio et vitae tenetur impedit
                voluptatum omnis consequatur voluptatem excepturi? Deleniti minus harum at consectetur voluptatem. Modi
                minus aperiam sint nobis, quasi nisi itaque provident ex illum est ut ab, blanditiis quam sequi.
                Tenetur, in repellat? Reiciendis temporibus aliquam molestiae odio rem perspiciatis, laudantium
                inventore reprehenderit incidunt similique voluptate fugiat possimus at, nulla velit odit corrupti
                aspernatur error consectetur. Voluptatibus nesciunt ut laudantium? Dolor nesciunt, rerum quia sed
                voluptatem voluptas sint!
            </p>
            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Neque temporibus, atque nulla quo ea vel quas
                nesciunt illo similique laudantium eligendi? Possimus assumenda, rerum error, facere natus vitae maiores
                sequi magnam magni dicta non quidem maxime quaerat voluptatem. Consequuntur vero sapiente sequi, laborum
                possimus ab qui quas aut esse hic.
            </p>
            <figure class="kitchen">
                <img src="../assets/images/kitchen.jpg" alt="">
                <figcaption>A konyhánk</figcaption>
            </figure>
            <p>
                Lorem ipsum dolor sit amet consectetur adipisicing elit. Aliquam nulla error dolorum unde. Soluta sint
                quis distinctio voluptate aliquid laboriosam explicabo velit impedit, tempora accusantium provident
                commodi temporibus est aut dolore iusto cum culpa quod saepe beatae, natus fuga id atque dolor? Sit, aut
                distinctio ex earum vitae fugit deserunt necessitatibus. A tempore facere iusto ratione sint sapiente
                deserunt ut quod. Obcaecati aspernatur quo totam a cumque, magnam possimus rerum quas, ipsa autem sunt
                quam? Temporibus ducimus nulla dolore, velit cumque laudantium tempore. Blanditiis, eligendi totam.
                Repudiandae quo earum error nulla maxime perspiciatis quis quia odit, sit deserunt voluptate placeat
                sint ipsum amet nam autem vitae reiciendis dolor inventore architecto soluta corrupti fugiat tempora.
                Enim cum ut at possimus unde?
            </p>

        </div>
    </div>
</template>

<style>
#about-us {
    background-color: var(--mainColor);
    overflow: auto;
    padding-bottom: 2rem;
}

#about-us figure.chef {
    float: right;
    margin-left: 1rem;
}

#about-us figure.chef img {
    height: 300px;
    width: auto;
}

#about-us figure.kitchen {
    float: left;
    margin-right: 1rem;
}

#about-us figure.kitchen img {
    height: 300px;
    width: auto;

}

#about-us figure {
    background-color: var(--secondaryColor);
    margin: 1rem 0;
}

#about-us figcaption{
    padding: 3px;
    text-decoration: underline;
}

figure.img {
    clear: both;
}
</style>