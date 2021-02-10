<script>
  let sections = [
    {
      id: "welcome",
    },
    {
      id: "vision",
      article: {
        title_en: "vision",
        title_ar: "رُؤْيَـتُـنـــا",
        text_en:
          "to remove the stigma of dark roasted coffee being burnt coffee",
        text_ar:
          "هي إزالة الوصمة حول أن حمصات القهوة الداكنة تعتبر قهوة محروقة",
      },
    },
    {
      id: "products",
      article: {
        title_en: "products",
        title_ar: "مُنـتَـجـاتُـنــــا",
        text_en:
          "we offer a range of the finest crops, in addition to special blends",
        text_ar: "نوفر مجموعة من أجود المحاصيل، بالإضافة إلى خلطات خاصة",
        items: [
          "https://media.zid.store/b32b646e-e783-482c-b26d-2cea92e04a83/29d865a3-0566-4c87-8ddd-b09f53c47b28.png",
          "https://media.zid.store/b32b646e-e783-482c-b26d-2cea92e04a83/14f4ac1c-8795-41e7-8dd4-58b3e6cf1951.png",
          "https://media.zid.store/b32b646e-e783-482c-b26d-2cea92e04a83/ee5221fb-9fb3-4e69-a478-777cbc00df23.png",
          "https://media.zid.store/b32b646e-e783-482c-b26d-2cea92e04a83/3e388a66-c0b8-4b65-b8a1-0ff535c472ae.png",
        ],
        extra_en: "and more on-demand...",
        extra_ar: "والمزيد حسب الطلب..."
      },
    },
    {
      id: "values",
      article: {
        title_en: "values",
        title_ar: "قِيَمُنــــــــا",
        text_en:
          "our first client is us, if we can't drink it, we can't sell it",
        text_ar: "عميلنا الأول هو نحن، إذا لم نتمكن من شربه، فلا يمكننا بيعه",
      },
    },
    {
      id: "team",
      article: {
        title_en: "team",
        title_ar: "فَريقنا",
        text_en:
          "consists of a people with shared passion for providing a distinctive coffee, and they mastered making, preparing and selling coffee",
        text_ar:
          "يتكون من أشخاص لديهم شغف مشترك لتقديم قهوة مميزة، وأتقنوا صنع القهوة وإعدادها وبيعها",
      },
    },
    {
      id: "services",
      article: {
        title_en: "services",
        title_ar: "خَــدَمـاتُـنـــا",
        text_en: `
          <ul>
            <li>supplying roasted coffee to speciality cafes, with custom roast -</li>
            <li>provide coffee tools, train baristas and latte art -</li>
            <li>Consulting services for startup cafes -</li>
          </ul>
          `,
        text_ar: `
          <ul>
            <li>- توريد القهوة المحمصة إلى المقاهي المتخصصة، مع حمصة مخصصة</li>
            <li>- توفير أدوات القهوة وتدريب باريستا وفن اللاتيه</li>
            <li>- خدمات استشارية للمقاهي الناشئة</li>
          </ul>
          `,
      },
    },
    {
      id: "location",
      article: {
        title_en: "location",
        title_ar: "عُنّوانُنــــــــــا",
        text_en: `
        we provide samples and coffee drinks at our location
        <br/><small>7892 abdullah ibn shahwin, al aqeeq, riyadh 13515</small`,
        text_ar: `
        يتم توفير عينات القهوة ومشروباتها في موقعنا
        <br/><small>7892 عبدالله بن شهوين، العقيق، الرياض 13515</small>`,
      },
    },
    {
      id: "thanks",
      assets: true
    },
  ];
</script>

<main lang="ar">
  {#each sections as { id, article, assets }, i}
    <section {id}>
      <article>
        {#if article}
          <h1 lang="en">{article.title_en}</h1>
          <h1>{article.title_ar}</h1>
          <p lang="en">{@html article.text_en}</p>
          <p>{@html article.text_ar}</p>
        {:else if assets}
          <div class="thanks" />
          <a class="btn btn-primary" href="https://store.perspective.cafe" target="_blank"><div class="store" /></a>
          <a class="btn btn-secondary" href="https://wa.me/966500211054" target="_blank"><div class="call" /></a>
          <a class="btn btn-secondary" href="https://g.page/perspective-cafe" target="_blank"><div class="map" /></a>
          <a class="btn btn-secondary" href="https://instagram.com/perspective.cafe" target="_blank"><div class="instagram" /></a>
        {:else}
          <div class="logo" />
          <a class="btn btn-primary" href="https://store.perspective.cafe" target="_blank"><div class="store" /></a>
          <a class="btn btn-secondary" href="https://wa.me/966500211054" target="_blank"><div class="call" /></a>
          <a class="btn btn-secondary" href="https://g.page/perspective-cafe" target="_blank"><div class="map" /></a>
        {/if}
        {#if article?.items}
        <br/>
        <div class="products">
          {#each article.items as item}
          <a href="https://store.perspective.cafe" target="_blank"><img src={item} alt="" /></a>
          {/each}
        </div>
        {/if}
        {#if article?.extra_en}
        <br/>
        <p lang="en">{@html article.extra_en}</p>
        <p>{@html article.extra_ar}</p>
        {/if}
      </article>
      {#if i + 2 > sections.length}
      <div>
        <a href="#{sections[i - 1]?.id}" class="box">
          <div class="arrow-up" />
        </a>
      </div>
      {:else if i === 0}
      <div>
        <a href="#{sections[i + 1]?.id}" class="box">
          <div class="arrow-down" />
        </a>
      </div>
      {:else}
        <div>
          <a href="#{sections[i + 1]?.id}" class="box">
            <div class="arrow-down" />
          </a>
          <a href="#{sections[i - 1]?.id}" class="box">
            <div class="arrow-up" />
          </a>
        </div>
      {/if}
    </section>
  {/each}
</main>
