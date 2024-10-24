<nav class="menu-genre text-center">
        <ul class="menu-theme">
            <li>
                <input type="checkbox" id="option1" />
                <label for="option1">
                    <img src={imgAlien} alt="Icône illustrant le dessin animé">
                    <span class="theme">Science-fiction</span>
                </label>
            </li>
            <li>
                <input type="checkbox" id="option2" />
                <label for="option2">
                    <img src={imgArme} alt="Icône illustrant le dessin animé">
                    <span class="theme">Thriller</span>
                </label>
            </li>
            <li>
                <input type="checkbox" id="option2" />
                <label for="option2">
                    <img src={imgAmour} alt="Icône illustrant le dessin animé">
                    <span class="theme">Romantique</span>
                </label>
            </li>
            <li>
                <input type="checkbox" id="option3" />
                <label for="option3">
                    <img src={imgDessinAnime} alt="Icône illustrant le dessin animé">
                    <span class="theme">Famillial</span>
                </label>
            </li>
        </ul>
    </nav>
<script>
    import imgDessinAnime from '$lib/assets/dessin-anime.png';
    import imgAlien from '$lib/assets/alien.png';
    import imgArme from '$lib/assets/arme.png';
    import imgAmour from '$lib/assets/amour.png';

</script>
<style>
.menu-genre {
    padding: 1rem 0;
    background-color: #25211e;
}

ul {
    display: flex;
    gap: 2rem;
    list-style: none;
    padding: 45px 0;
    margin: 0;
    justify-content: center;
}

li {
    label {
        display: flex;
        align-items: center;
        flex-direction: column;
        gap: 0.5rem;
        cursor: pointer;
        color: #e0e0e0;
        font-weight: bold;
        transition: all 0.3s ease;
    }

    img {
        width: 60px;
        height: 60px;
        object-fit: cover;
        filter: grayscale(40%);
        transition: all 0.3s ease;
        border: 2px solid transparent;
    }

    input[type="checkbox"] {
        display: none;
    }

    label:hover,
    label:focus-within {
        transform: translateY(-5px);
        color: #d2ae12;
    }

    label:hover img,
    label:focus-within img {
        border-radius: 50%;
        border-color: #d2ae12;
        box-shadow: 0 0 10px rgba(210, 174, 18, 0.5);
    }
    .theme {
        color: #d2ae12;
        font-weight: 700;
    }
}
</style>
