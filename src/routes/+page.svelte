<script>
  import Navbar from "$lib/Navbar.svelte";
  import { Button, Col, Row } from "@sveltestrap/sveltestrap";
  import Widget from "$lib/Widget.svelte";

  // Contoh 1 : akses variabel
  let count = 0;
  function plus() {
    count += 1;
  }

  // Contoh 2 : akses data array
  let skill = {
    namaSkill: ["Svelte", "PHP", "VueJS"],
    ratingSkill: 10,
  };

  // Contoh 3 : akses image
  let imageURL = "images/gambar1.jpg";
</script>

<main>
  <main class="flex flex-col space-y-8 p-8">
    <h1 class="text-3xl font-bold text-center mb-8">
      Scroll Down untuk Lihat Animasi
    </h1>

    <!-- Beberapa konten di atas untuk memberi ruang menggulir -->
    <div style="height: 800px;"></div>

    <!-- Gunakan Widget dengan komponen lain di dalamnya -->
    <Widget title="Widget 1: Menarik!">
      <div class="p-4 bg-gray-200 rounded shadow-md">
        <p>data</p>
      </div>
      <!-- Komponen lain di dalam widget -->
    </Widget>

    <!-- Widget dengan gambar -->
    <Widget title="Widget 1: Gambar di dalam Widget">
      <img src="images/gambar1.jpg" alt="Gambar" class="w-full rounded-lg" />
    </Widget>

    <!-- Beberapa konten lagi untuk memberi ruang menggulir -->
    <div style="height: 500px;"></div>
  </main>

  <Navbar />

  <Row>
    <Col>
      <Button color="primary" outline>Hello World!</Button>
    </Col>
  </Row>

  <h1>Welcome to SvelteKit</h1>
  <p>
    Visit <a href="https://svelte.dev/docs/kit">svelte.dev/docs/kit</a> to read the
    documentation
  </p>

  <!-- // contoh 1 -->
  <h1>{count}</h1>
  <button on:click={plus}>+</button>

  <!-- Contoh 2 -->
  <!-- Output : Skill : PHP & 10 -->
  <p>Skill : {skill.namaSkill[1]} & {skill.ratingSkill}</p>

  <!-- Contoh 3 -->
  <img src={imageURL} alt="Gambar" width="300" />
</main>
