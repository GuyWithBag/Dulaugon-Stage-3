<script lang="ts">
    export let avatar: string
    export let id: string
    export let email: string
    export let name: string 

    import '$lib/fonts.css' 

</script>

<div class=" gap-1 shadow-lg rounded-xl p-9 bg-teal-200 flex flex-col items-center justify-center w-80">
    <div class="p-2">
        <img 
            class=" object-cover w-16 h-16 rounded-full"
            src={avatar}
            alt="img"
        />
    </div>
    <p class=" font-[vanilla-ravioli] text-gray-700"><span class=" text-gray-500">#</span>{id}</p>
    <p class=" font-[saturday] text-3xl">{name}</p>
    <a class=" font-[vanilla-ravioli] text-sm" href="mailto:{email}?subject=Your%20Subject&body=Your%20Message%20Goes%20Here">{email}</a>
</div> 

