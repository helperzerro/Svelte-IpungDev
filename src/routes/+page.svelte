<script>
  import Navbar from '$lib/Navbar.svelte';
    import { Button, Col, Row } from '@sveltestrap/sveltestrap';

    // Contoh 1 : akses variabel
        let count = 0
    function plus() {
        count+=1
    }

    // Contoh 2 : akses data array
let skill = {
        namaSkill :["Svelte", "PHP","VueJS"],
        ratingSkill:10
    }

    // Contoh 3 : akses image
    let imageURL ="images/gambar1.jpg"
</script>

<main>
    <Navbar/>

        <Row>
        <Col>
            <Button color="primary" outline>Hello World!</Button>
        </Col>
    </Row>

    <h1>Welcome to SvelteKit</h1>
    <p>Visit <a href="https://svelte.dev/docs/kit">svelte.dev/docs/kit</a> to read the documentation</p>



    <!-- // contoh 1 -->
    <h1>{count}</h1>
    <button on:click={plus}>+</button>

    <!-- Contoh 2 -->
    <!-- Output : Skill : PHP & 10 -->
    <p>Skill : {skill.namaSkill[1]} & {skill.ratingSkill}</p>

    <!-- Contoh 3 -->
    <img src={imageURL} alt="Gambar" width="300"/>
</main>