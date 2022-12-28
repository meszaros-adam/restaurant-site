<template>
    <div class="contact" id="contact">
        <div>
            <h1>Kapcsolat:</h1>
            <ul>
                <li>
                    Telefon: +363213827
                </li>
                <li>
                    Cím: 9400, Sopron, Kitalált utca 2
                </li>
                <li>
                    Email: kitalalt-etterem@gmail.com
                </li>
                <li>
                    Fax: 1020123412
                </li>
            </ul>
        </div>
        <div class="map">
            <h1>Térkép:</h1>
            <div class="map-responsive">
                <iframe
                    src="https://www.google.com/maps/embed?pb=!1m14!1m12!1m3!1d2059.150999016125!2d16.59310988145115!3d47.68467112874398!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!5e1!3m2!1shu!2shu!4v1672216356143!5m2!1shu!2shu"
                    width="600" height="450" style="border:0;" allowfullscreen></iframe>
            </div>

        </div>
    </div>
</template>

<style>
.contact {
    margin: 2rem;
    display: flex;
    justify-content: space-around;
}

.contact li {
    list-style: none;
    margin-bottom: 2rem;
}

.contact li::before {
    content: '';
    display: inline-block;
    height: 2rem;
    aspect-ratio: 1;
    background-image: url('../assets/images/No-Image-Placeholder.svg.png');
    background-size: contain;
}

.map {
    width: 50%;
}

.map-responsive {
    overflow: hidden;
    padding-bottom: 56.25%;
    position: relative;
    height: 0;
}

.map-responsive iframe {
    left: 0;
    top: 0;
    height: 100%;
    width: 100%;
    position: absolute;
}

@media screen and (max-width: 992px) {
    .contact {
        flex-direction: column;
    }

    .map {
        width: auto;
    }

}
</style>
