<script>
    import Header from "./UI/Header.svelte";
    import MeetupGrid from "./Meetups/MeetupGrid.svelte";

    const meetups = [
        {
            id: "m1",
            title: "Coding Bootcamp",
            subtitle: "Learn to code in 2 hours",
            description:
                "In this meetup, we will have some experts that teach you how to code.",
            imageUrl:
                "https://www.apple.com/newsroom/images/product/services/standard/Apple-Computer-Science-Education-Week-Keep-on-Coding_big.jpg.large.jpg",
            address: "27th Nerd Road, 32523 New York",
            contactEmail: "code@test.com",
        },
        {
            id: "m2",
            title: "Swim Together",
            subtitle: "Let's go for some swimming",
            description: "We will simply swim some rounds!",
            imageUrl:
                "https://aquamermaid.com/cdn/shop/products/Aquamermaid_meetup_5d48595d-225d-413d-8177-f52ac04d2d5f.png?v=1606095586",
            address: "27th Nerd Road, 32523 New York",
            contactEmail: "swim@test.com",
        },
    ];
</script>

<Header />

<main>
    <MeetupGrid {meetups} />
</main>

<style>
    main {
        margin-top: 5rem;
    }
</style>
