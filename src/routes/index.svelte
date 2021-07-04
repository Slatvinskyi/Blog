<script context="module">

export const load = async({fetch}) => {
    const res = await fetch("https://jsonplaceholder.typicode.com/posts")
    const posts = await res.json();
    return {
        props: {
            posts,

        },
    };
};
</script>

<script>
    export let posts;
</script>

<h1>Posts</h1>

<div class="posts">
    {#each posts as item}
    <div class="post">
        <h2>{item.title.substring(0, 20)}</h2>
        <p>{item.body.substring(0, 80)}</p>
        <p class="link"><a sveltekit:prefetch href={`/blog/${item.id}`}>read more</a></p>
    </div>
    {/each}
</div>

<style>
    .posts {
        display: grid;
        grid-template-columns: 1fr 1fr;
        grid-gap: 20px;

    }

    .post {
        padding: 10px;
        border: 1px solid #ddd;
    }

    h2 {
        margin: 0;
        box-shadow: 0 0 15px #eee;
    }

    .link {
        text-align: right;
    }
    </style>
