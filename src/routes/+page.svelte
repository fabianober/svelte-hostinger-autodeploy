<script>
    import { goto } from '$app/navigation';
    import { Button, Card, Input, Heading, P, A, List, Li } from 'flowbite-svelte';
    
    let counter = 0;
    let blogId = "";

    function increment() {
        counter += 1;
    }

    function navigateToBlog() {
        if (blogId.trim()) {
            goto(`/blog/${encodeURIComponent(blogId.trim())}`);
        }
    }

    function handleKeyPress(event) {
        if (event.key === 'Enter') {
            navigateToBlog();
        }
    }
</script>

<main class="container mx-auto px-4 py-8 max-w-5xl">
    <Heading tag="h1" class="mb-6 text-center dark:text-white" customSize="text-4xl">Svelte Auto-Deploy for Hostinger Demo</Heading>
    
    <Card class="mb-8 !max-w-none" padding="xl">
        <Heading tag="h2" class="mb-4" customSize="text-2xl">About This Project</Heading>
        <P class="mb-4">
            This is a demonstration of automatic deployment of a Svelte app to a Hostinger shared hosting server using GitHub Actions and webhooks.
            Every push to the main branch triggers a build and deployment process.
        </P>
        <P class="mb-4">Key Features:</P>
        <List tag="ul" class="mb-4 space-y-2" list="disc">
            <Li>Automatic deployment on GitHub push</Li>
            <Li>GitHub Actions workflow integration</Li>
            <Li>Hostinger shared hosting compatible</Li>
            <Li>Zero-downtime deployment</Li>
        </List>
        <div class="mb-4">
            <P class="font-semibold mb-2">Useful Links:</P>
            <div class="flex flex-col gap-2">
                <A href="https://github.com/fabianober/svelte-hostinger-autodeploy">→ GitHub Repository</A>
                <A href="https://github.com/annshiv/Hostinger-deployment">→ Deployment Guide</A>
                <A href="https://fabian-ober.de">→ Visit My Website for interesting projects</A>
            </div>
        </div>
    </Card>

    <Card class="mb-8 !max-w-none" padding="xl">
        <Heading tag="h2" class="mb-4" customSize="text-2xl">Demo Counter</Heading>
        <P class="mb-4">Click the button below to see the app in action. Any changes to this counter will be lost on refresh, as this is just a demo of the deployment process.</P>
        <Button size="xl" color="blue" pill={true} on:click={increment}>
            Clicked {counter} times
        </Button>
    </Card>

    <Card class="!max-w-none" padding="xl">
        <Heading tag="h2" class="mb-4" customSize="text-2xl">Blog Navigation</Heading>
        <P class="mb-4">Enter a blog ID to navigate without page refresh:</P>
        <div class="flex gap-4 items-center mb-4">
            <Input
                size="lg"
                bind:value={blogId}
                placeholder="Enter blog ID (e.g. 1, 2, 3...)"
                on:keypress={handleKeyPress}
                class="flex-1"
            />
            <Button size="lg" color="blue" on:click={navigateToBlog}>
                Go to Blog
            </Button>
        </div>
        <P size="sm" color="text-gray-600" class="dark:text-gray-400">
            Quick links: 
            <Button color="alternative" class="ml-2" size="xs" on:click={() => goto('/blog/1')}>Blog 1</Button>
            <Button color="alternative" class="ml-2" size="xs" on:click={() => goto('/blog/2')}>Blog 2</Button>
            <Button color="alternative" class="ml-2" size="xs" on:click={() => goto('/blog/3')}>Blog 3</Button>
        </P>
    </Card>
</main>