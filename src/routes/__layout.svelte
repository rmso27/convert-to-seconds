<script>
    import Footer from "../components/Footer.svelte"
    import "../public/css/style.css"
</script>

<div class = "main">
    <div class = "main-wrapper">
        <slot></slot>
    </div>
    <div class = "footer">
        <Footer/>
    </div>
</div>