<script>
    import { Button, Card, Heading, P, List, Li } from 'flowbite-svelte';
    export let data;
</script>

<main class="container mx-auto px-4 py-8 max-w-5xl">
    <Card class="!max-w-none" padding="xl">
        <Heading tag="h1" class="mb-6" customSize="text-4xl">Blog Post {data.slug}</Heading>
        <P class="mb-6">You navigated to this page using client-side routing - notice how there was no page refresh!</P>
        
        <div class="prose max-w-none dark:prose-invert">
            <P class="mb-4">
                This is a dynamic route demonstration. The current blog ID is: 
                <code class="bg-gray-100 dark:bg-gray-800 px-2 py-1 rounded">{data.slug}</code>
            </P>
            <P>Try these things:</P>
            <List tag="ul" class="mb-6 space-y-2" list="disc">
                <Li>Notice the URL updates without page refresh</Li>
                <Li>Use browser back/forward buttons - they work seamlessly</Li>
                <Li>Refresh the page - it still works (server-side rendering)</Li>
            </List>
        </div>

        <Button href="/" size="xl" color="blue" pill={true}>← Back to Home</Button>
    </Card>
</main> 