<script>
  import ListItem from "$lib/ListItem.svelte";
  import Welcome from "$lib/Welcome.svelte";
  import {
    Container,
    Row,
    Col,
    ListGroup,
    Table,
  } from "@sveltestrap/sveltestrap";

  const newLaptop = {
    product: "Asus Gaming",
    desc: "Laptop Gaming Keren",
  };

  let user = {
    username: "Jax",
    role: 3,
  };

  let userTabel = [
    {
      id: "uud1",
      firstname: "Joko",
      lastname: "Maris",
      username: "joe",
    },
    {
      id: "uud2",
      firstname: "Dada",
      lastname: "Vars",
      username: "DV",
    },
    {
      id: "uud3",
      firstname: "Laris",
      lastname: "Kari",
      username: "LK",
    },
  ];
</script>

<Container>
  <h1 class="bg-amber-300 text-3xl font-bold underline">Hello world!</h1>

  <Table>
    <thead>
      <tr>
        <th>#</th>
        <th>First Name</th>
        <th>Last Name</th>
        <th>Username</th>
      </tr>
    </thead>
    <tbody>
      {#each userTabel as u, i (u.id)}
        <tr>
          <th scope="row">{i + 1}</th>
          <td>{u.firstname}</td>
          <td>{u.lastname}</td>
          <td>{u.username}</td>
        </tr>
      {/each}
    </tbody>
  </Table>

  <Welcome user={user.username} role={user.role} />
  <Row>
    <Col>
      <ListGroup>
        <ListItem product={"Mac"} desc={"Apple"} />
        <ListItem {...newLaptop} />
      </ListGroup>
    </Col>
  </Row>
</Container>
