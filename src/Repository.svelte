<script>
    export let item;
</script>
<style>
    #repo {
        border-top: 1px solid #828282;
        padding: 10px;
        width: 500px;
        margin-top: 15px;
    }
    header {
        font-family: 'Roboto', sans-serif;
        font-weight: 500;
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        margin-bottom: 10px;
    }
    #name,a {
        font-size: 25px;
        color: #4578AA;
        cursor: pointer;
        transition: 0.2s;
        overflow: hidden;
        text-overflow: ellipsis;
        white-space: nowrap;
    }
    #name:hover {
        color: rgb(113, 152, 192);
    }
    #stars {
        font-size: 25px;
        white-space: nowrap;
    }
    content {
        font-family: 'Roboto', sans-serif;
    }
</style>
<div id="repo">
    <header>
        <div id="name"><a href={item.html_url}>{item.full_name}</a></div>
        <div id="stars">{'★ ' + item.stargazers_count}</div>
    </header>
    <content>
        {item.description}
    </content>
</div>