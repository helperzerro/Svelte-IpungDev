<script>
  import { Col, ListGroupItem, Row } from "@sveltestrap/sveltestrap";

  // export digunakan di sini untuk memastikan bahwa variabel yang dideklarasikan bisa diakses dan diberikan nilai dari luar komponen.
  export let product;
  export let desc;
</script>

<ListGroupItem>
  <Row>
    <Col>
      <img src="images/gambar1.jpg" alt="Gambar1" width="100" />
    </Col>
    <Col>
      <h5>{product}</h5>
      <p>{desc}</p>
    </Col>
  </Row>
</ListGroupItem>
