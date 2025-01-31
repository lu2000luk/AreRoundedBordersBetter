<script>
    //@ts-nocheck

    import { browser } from "$app/environment";
    import { onMount } from 'svelte';

    const titleString = "Are rounded borders better?";
    const titleArray = titleString.split("");

    let letterElements;

    onMount(() => {
        if (browser) {
            letterElements = document.querySelectorAll(".title-letter");
            
            setInterval(() => {
                letterElements.forEach(element => {
                    if (Math.random() > 0.5) {
                        element.style.fontFamily = '"Domine", serif';
                    } else {
                        element.style.fontFamily = '"Roboto", serif'; 
                    }
                });
            }, 250)

        }
    });

    const downloadFiles = [
        {
            name: "Example 1",
            files: {
                rounded_project: "projects/Example 1 Rounded.penpot",
                sharp_project: "projects/Example 1 Sharp.penpot",
                rounded_image: "example_1_rounded.png",
                sharp_image: "example_1_sharp.png"
            }
        },
        {
            name: "Example 2",
            files: {
                rounded_project: "projects/Example 2 Rounded.penpot",
                sharp_project: "projects/Example 2 Sharp.penpot",
                rounded_image: "example_2_rounded.png",
                sharp_image: "example_2_sharp.png"
            }
        },
        {
            name: "Example 3",
            files: {
                rounded_project: "projects/Example 3 Rounded.penpot",
                sharp_project: "projects/Example 3 Sharp.penpot",
                rounded_image: "example_3_rounded.png",
                sharp_image: "example_3_sharp.png"
            }
        }
    ];
</script>

<svelte:head>
    <title>AreRoundedBordersBetter?</title>
</svelte:head>

<div class="homesection m-4 h-page-less">
        <h1 class="title text-6xl mt-40 mx-20">
                {#each titleArray as letter}
                        <span class="title-letter">{letter}</span>
                {/each}
        </h1>

        <p class="text-2xl mx-20 mt-10">This is an interactive debate on whether you should use rounded or sharp border in your web pages.</p>
        <p class="text-xl mx-20 mt-2">Made with ❤️ by <a href="https://lu2000luk.com" class="underline decoration-sky-500 decoration-wavy hover:bg-white rounded bg-opacity-15 transition-all hover:p-2 hover:text-gray-800">lu2000luk</a></p>
</div>
<p class="flex flex-col-reverse domine-400 mx-24">(Scroll down)</p>
<div class="separator"></div>
<div class="opinions mx-24">
        <h2 class="text-4xl mt-8 font-bold">My opinions</h2>
        <p class="text-xl mt-4">
            I really love <b>rounded</b> borders. They make the page look more friendly and welcoming. <br>
            Recently, I made a little website just containing text. It had a white, soft, background and a gray dotted grid in the background. <br>
            It had black Times New Roman text and some images on the side of it. <br>
            I also made a bottom section containing the text author and the date of the last update. <br>
            I used <b>rounded borders</b> for the images and the bottom section. <br>
            It looked <b>ugly</b>. <br>
            The text and the title where to serious and calm that the rounded borders made it look like a joke. <br>
            I changed the borders to sharp and it looked much better. <br>
            This sparked me the idea of making this page. <br>
            I will gradually show various examples of pages and borders and you will decide which one is better. <br>
            I will also sprinkle some of my opinions here and there. <br>
        </p>
</div>

<div class="example-1 mx-24">
        <h2 class="text-4xl mt-8 font-bold">Example 1</h2>
        <p class="text-xl mt-4 mb-2">
            This is an example landing page for a fictional gaming company. (Ignore the bad UI its a prototype) <br>
        </p>
        <div class="images flex gap-3 justify-center mt-5 mb-2">
            <img src="example_1_rounded.png" width="40%" alt="Rounded borders">
            <img src="example_1_sharp.png" width="40%" alt="Sharp borders">
        </div>
        <p class="text-xl mt-4">
            Which one do you prefer? <br>
            I prefer the <b>rounded</b> one. <br>
            The sharp one looks too serious and professional. <br>
            At the end of the day we are targeting <i>gamers</i>... <br>
        </p>
</div>

<div class="example-2 mx-24">
        <h2 class="text-4xl mt-8 font-bold">Example 2</h2>
        <p class="text-xl mt-4 mb-2">
            This is an example blog. (As always ignore the bad UI) <br>
        </p>
        <div class="images flex gap-3 justify-center mt-5 mb-2">
            <img src="example_2_rounded.png" width="40%" alt="Rounded borders">
            <img src="example_2_sharp.png" width="40%" alt="Sharp borders">
        </div>
        <p class="text-xl mt-4">
            In this case i also changed fonts to match the border style. <br>
            Which one do you prefer? <br>
            I prefer the <b>rounded</b> one. <br>
            The sharp one looks too serious and professional for the <i>eye-killing</i> colors. <br>
            Plus, the website feels and is very friendly. <br>
            Sharp borders ≠ friendly at all. <br>
            I think of somewhere safe, secure and professional when i see sharp borders. <br>
        </p>
</div>

<div class="example-3 mx-24">
        <h2 class="text-4xl mt-8 font-bold">Example 3</h2>
        <p class="text-xl mt-4 mb-2">
            This is an example login page. (The UI is good this time)<br>
        </p>
        <div class="images flex gap-3 justify-center mt-5 mb-2">
            <img src="example_3_rounded.png" width="40%" alt="Rounded borders">
            <img src="example_3_sharp.png" width="40%" alt="Sharp borders">
        </div>
        <p class="text-xl mt-4">
            In this case i prefer the <b>sharp</b> one. <br>
            The rounded one looks too playful for a login page. <br>
            We are talking about security here, no time for games. <br>
            (All jokes aside the sharp one looks more professional but the rounded one doesn't look bad at all) <br>
        </p>
</div>

<div class="separator"></div>

<div class="downloads mx-24">
        <h2 class="text-4xl mt-8 font-bold">Project files downloads</h2>
        <p class="text-xl mt-4 mb-2">
            All of these designs where made on <a href="https://penpot.app/" class="underline decoration-sky-500 decoration-wavy hover:bg-white rounded bg-opacity-15 transition-all hover:p-2 hover:text-gray-800">Penpot</a><br>
            You can download the project files here: <br>
        </p>
        <div class="download-files">
            {#each downloadFiles as downloadFile}
                <div class="download-file mt-2">
                    <h3 class="text-2xl font-bold">{downloadFile.name}</h3>
                    <a href={downloadFile.files.rounded_project} download><button class="m-2 hover:bg-white rounded-lg bg-opacity-15 transition-all border-2 border-sky-500 p-2 hover:text-gray-800">Rounded project</button></a>
                    <a href={downloadFile.files.sharp_project} download><button class="m-2 hover:bg-white bg-opacity-15 transition-all border-2 border-sky-500 p-2 hover:text-gray-800">Sharp project</button></a>

                    <a href={downloadFile.files.rounded_image} download><button class="m-2 hover:bg-white rounded-lg bg-opacity-15 transition-all border-2 border-sky-500 p-2 hover:text-gray-800">Rounded image</button></a>
                    <a href={downloadFile.files.sharp_image} download><button class="m-2 hover:bg-white bg-opacity-15 transition-all border-2 border-sky-500 p-2 hover:text-gray-800">Sharp image</button></a>
                </div>
            {/each}
        </div>
</div>

<div class="m-10"></div>
