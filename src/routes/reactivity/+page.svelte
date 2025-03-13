<script>
  import Navbar from "$lib/Navbar.svelte";
  import { Row, Col, Button } from "@sveltestrap/sveltestrap";

  let keranjang = 0;
  let harga = 100000;

  let diskon = {
    diskon3: 0.1,
    diskon10: 0.3,
  };

  // ketika user klik ad to cart, harga total tidak berubah karena belum reactive, maka jangan pakai let tapi $:
  //   let hargatotal = keranjang * harga;
  $: hargatotal = keranjang * harga;

  $: if (keranjang >= 10) {
    hargatotal = keranjang * harga - keranjang * harga * diskon.diskon10;
  } else if (keranjang >= 3) {
    hargatotal = keranjang * harga - keranjang * harga * diskon.diskon3;
  } else {
    hargatotal;
  }

  function tambahKerangjang() {
    keranjang += 1;
  }
</script>

<Navbar />
<br />

<container>
  <Row>
    <Col>
      <Button on:click={tambahKerangjang} color="primary" outline
        >Add to Cart</Button
      >
    </Col>
    <Col>
      {keranjang}<br />
      harga total : Rp. {hargatotal}
    </Col>
  </Row>
</container>
