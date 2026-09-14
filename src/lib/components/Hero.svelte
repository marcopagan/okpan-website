<script lang="ts">
    import { IconChevronDown, IconArrowUpRight } from '@tabler/icons-svelte';
    import { Dialog  } from '@skeletonlabs/skeleton-svelte';
	import DownloadModal from './DownloadModal.svelte';
	import MobileModal from './MobileModal.svelte';
    import { base } from '$app/paths';
</script>

<section class="container mx-auto px-0 md:px-16">
    <div class="hero h-700 sm:rounded-lg relative overflow-hidden">

        <video autoplay disablepictureinpicture loop muted class="w-full h-full absolute object-cover -z-5">
            <source src={`${base}/brand/hero-vid.mp4`} type="video/mp4" />
        </video>

        <div class="flex flex-col flex-wrap gap-24 text-center justify-center items-center content-center px-16 md:px-48 h-full z-8">
            <h3 class="h1 leading-[1]">A tool for reconnecting dispersed collections</h3>
            <p>Ọkpan brings together records of artefacts scattered across museums worldwide, reconnecting them with the communities, knowledge, and histories they were separated from.</p>

            <div class="download-desktop hidden md:inline">
                <Dialog>
	                <Dialog.Trigger class="btn preset-filled bg-primary-800 px-32 py-16 gap-8 hover:gap-12">
                        Download
                        <IconChevronDown class="size-18 transition" stroke="1.5"/>
                    </Dialog.Trigger>
                    <DownloadModal />
                </Dialog>
            </div>

            <div class="download-mobile inline md:hidden">
                <Dialog>
	                <Dialog.Trigger class="btn preset-filled bg-primary-800 px-32 py-16 gap-8 hover:gap-12">
                        Get it
                        <IconArrowUpRight class="size-18 transition" stroke="1.5"/>
                    </Dialog.Trigger>
                    <MobileModal />
                </Dialog>
            </div>
        </div>
    </div>

</section>
