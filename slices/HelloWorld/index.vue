<template>
  <section
    class="md:flex md:items-stretch rounded-lg overflow-hidden shadow-2xl bg-white m-5"
  >
    <picture class="flex-1">
      <prismic-image :field="slice.primary.image" class="object-cover h-full w-full" />
    </picture>
    <article class="flex-1">
      <div class="p-8 flex flex-col h-full justify-between space-y-8">
        <div class="space-y-8">
          <h1
            class="font-bold text-2xl md:text-4xl leading-snug text-orange-600"
          >
            {{ $prismic.asText(slice.primary.title) }}
          </h1>
          <prismic-rich-text :field="slice.primary.description" />
        </div>
        <div class="text-center md:flex md:flex-col md:items-end">
          <prismic-link
            :field="slice.primary.ctaLink"
            class="bg-orange-600 hover:bg-orange-700 transition-colors duration-300 ease-in-out text-white block px-8 py-4 font-bold rounded-lg"
          >
            {{ slice.primary.ctaLabel }}
          </prismic-link>
        </div>
      </div>
    </article>
  </section>
</template>
<script>
export default {
  props: {
    slice: {
      type: Object,
      required: true,
      default() {
        return {}
      }
    }
  },
}
</script>