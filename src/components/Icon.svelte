<script>
    export let name;
    const icons = [
        {
            name: "check-mark",
            path: "+"
        },
        {
            name: "delete",
            path: "x"
        }
    ]

    let icon = icons.find(item => item.name === name)

</script>