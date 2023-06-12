<script>
    import {onMount} from 'svelte'

    import Header from '../components/Header.svelte'
    import Main from '../components/Main.svelte'
    import TimeLine from '../components/TimeLine.svelte'
    import Sidebar from '../components/Sidebar.svelte'

    let data = {
        user: {
            nickname: "HenryD5",
            name: "Henry Yavi"
        },
        posts: [
            {
                username: "Elmo.pug",
                location: "Piura, Perú",
                avatar: "https://arepa.s3.amazonaws.com/elmo.jpg",
                photo: "https://arepa.s3.amazonaws.com/elmo002.jpg",
                like: false,
                bookmark: false,
                postComment: "Disfrutando de mi piscina",
                comments: [
                    {
                        id: 12223,
                        text: "Hola ELMO",
                        username: "Crispeta"
                    },
                    {
                        id: 12223,
                        text: "Hola!!",
                        username: "Dollarsin"
                    }
                ]
            },
            {
                username: "Elmo2.pug",
                location: "Piura, Perú",
                avatar: "https://arepa.s3.amazonaws.com/elmo.jpg",
                photo: "https://arepa.s3.amazonaws.com/elmo002.jpg",
                like: false,
                bookmark: false,
                postComment: "Disfrutando de mi piscina ...",
                comments: [
                    {
                        id: 12223,
                        text: "Hola ELMO",
                        username: "Crispeta"
                    }
                ]
            }
        ]
    }
    const API = "https://dog.ceo/api/breed/hound/images/random/3"

    onMount(async () => {
        //const response = await fetch(API);
        //data = await response.json();
        //console.log(data)
    })
</script>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Lato:wght@300;400&display=swap');
    @import url('https://fonts.googleapis.com/css2?family=Pacifico&display=swap');

    :global(body) {
      background-color: #fafafa;
      color: rgba(38, 38, 38, 0.7);
      font-family: "Lato", sans-serif;
      margin: 0;
      padding: 0;
    }
    :global(h1, h2, h3) {
        margin: 0;
        padding: 0;
    }
</style>

<Header />
<Main>
    <TimeLine posts={data.posts} />
    <Sidebar {...data.user} />
</Main>