<script lang="ts">
	import Card from "$lib/components/card.svelte"
    import portrait from "$lib/assets/images/portraits/portrait.jpg" 
    import Person from '$lib/classes/person'

    let personList: Person[] = [
        new Person(
            "Bluth, George", 
            "george.bluth@reques.in", 
            portrait
        ), 
        new Person(
            "Weaver, Janeth", 
            "janet.weaver@reques.in", 
            portrait
        ), 
        new Person(
            "Wong, Emma", 
            "emma.wong@reques.in", 
            portrait
        ), 
        new Person(
            "Holt, Eve", 
            "eve.holt@reques.in", 
            portrait
        ), 
        new Person(
            "Morris, Charles", 
            "charles.morris@reques.in", 
            portrait
        ), 
        new Person(
            "Ramos, Tracey", 
            "tracey.ramosh@reques.in", 
            portrait
        ), 
        new Person(
            "Lawson, Michael", 
            "michael.lawson@reques.in", 
            portrait
        ), 
        new Person(
            "Ferguson, Lindsay", 
            "lindsay.ferguson@reques.in", 
            portrait
        ), 
        new Person(
            "Funke, Tobias", 
            "tobias.funke@reques.in", 
            portrait
        ), 
        new Person(
            "Fields, Byron", 
            "byron.fields@reques.in", 
            portrait
        ), 
        new Person(
            "Edwards, George", 
            "george.edwards@reques.in", 
            portrait
        ), 
        new Person(
            "Howell, Rachel", 
            "rachel.howell@reques.in", 
            portrait
        ), 
    ]

    let amountShowing: number = 3
    let amountToShow: number = 3
    
    let hasMoreToShow: boolean = true

    function showMore(): void {
        if (amountShowing < personList.length) {
            amountShowing += amountToShow
        } 
        hasMoreToShow = amountShowing < personList.length
    }

</script>

<div class="flex flex-col gap-5 items-center content-center justify-center p-10 lg:p-20">
    <div class="flex items-center content-center justify-center">
        <div class="grid grid-cols-2 lg:grid-cols-3 gap-5"> 
            {#each personList as person, index}
                {#if index < amountShowing}
                    <Card 
                        avatar="{person.avatar}"
                        id="{(index + 1).toString()}" 
                        name="{person.name}"
                        email="{person.email}"
                    />
                {/if}
            {/each}
        </div>
    </div>
    {#if hasMoreToShow}
        <button class="rounded-lg bg-teal-200 w-36 h-16 text-center shadow-lg" on:click={showMore}>
            LOAD MORE
        </button>
    {:else}
        <button class="rounded-lg bg-teal-200 w-36 h-16 text-center shadow-lg text-gray-400" on:click={showMore}>
            No Data
        </button>
    {/if}
</div>



