<script>
    import Header from "./UI/Header.svelte";
    import MeetupGrid from "./Meetups/MeetupGrid.svelte";
    import TextInput from "./UI/TextInput.svelte";
    import Button from "./UI/Button.svelte";

    let title = "";
    let subtitle = "";
    let address = "";
    let imageUrl = "";
    let email = "";
    let description = "";

    let meetups = [
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

    function addMeetup() {
        const newMeetup = {
            id: Math.random().toString(),
            title,
            subtitle,
            address,
            imageUrl,
            contactEmail: email,
            description,
        };

        meetups = [newMeetup, ...meetups];
    }
</script>

<Header />

<main>
    <form on:submit|preventDefault={addMeetup}>
        <TextInput
            id="title"
            label="Title"
            type="text"
            value={title}
            on:input={(event) => (title = event.target.value)}
        />
        <TextInput
            id="subtitle"
            label="Subtitle"
            type="text"
            value={subtitle}
            on:input={(event) => (subtitle = event.target.value)}
        />
        <TextInput
            id="address"
            label="Address"
            type="text"
            value={address}
            on:input={(event) => (address = event.target.value)}
        />
        <TextInput
            id="imageUrl"
            label="Image URL"
            type="text"
            value={imageUrl}
            on:input={(event) => (imageUrl = event.target.value)}
        />
        <TextInput
            id="email"
            label="E-Mail"
            value={email}
            type="email"
            on:input={(event) => (email = event.target.value)}
        />
        <TextInput
            id="description"
            controlType="textarea"
            label="Description"
            value={description}
            on:input={(event) => (description = event.target.value)}
        />
        <Button type="submit" caption="Save" />
    </form>
    <MeetupGrid {meetups} />
</main>

<style>
    main {
        margin-top: 5rem;
    }

    form {
        width: 30rem;
        max-width: 90%;
        margin: auto;
    }
</style>
