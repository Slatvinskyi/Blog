<div class="container">
    <nav>
        <ul>
            <li>
                <a href="/">home</a>
            </li>
        </ul>
    </nav>
    <slot />
</div>

<style>
    .container {
        max-width: 800px;
        margin: 50px auto;
    }

    ul {
        display: flex;
        list-style: none;
        padding: 0;

    }

    li {
        margin: 10px;
    }

    
</style>