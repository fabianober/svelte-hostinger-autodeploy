<!--
 Copyright 2024 fabianober
 
 Licensed under the Apache License, Version 2.0 (the "License");
 you may not use this file except in compliance with the License.
 You may obtain a copy of the License at
 
     http://www.apache.org/licenses/LICENSE-2.0
 
 Unless required by applicable law or agreed to in writing, software
 distributed under the License is distributed on an "AS IS" BASIS,
 WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
 See the License for the specific language governing permissions and
 limitations under the License.
-->

<script>
    import "../app.css";
    import { DarkMode } from 'flowbite-svelte';
    import { onMount } from 'svelte';

    // Initialize theme from localStorage or system preference
    onMount(() => {
        if (localStorage.theme === 'dark' || (!('theme' in localStorage) && window.matchMedia('(prefers-color-scheme: dark)').matches)) {
            document.documentElement.classList.add('dark');
        } else {
            document.documentElement.classList.remove('dark');
        }
    });
</script>

<div class="min-h-screen transition-colors duration-300 dark:bg-gray-900">
    <div class="fixed top-4 right-4 z-50">
        <DarkMode />
    </div>
    <slot />
</div>