## Questions & Answers

### On this page you can find answers to the most frequently asked questions

<details>
<summary><b>How do I connect to MW Feed when I am using MW seed?</b></summary>

</br>

MW-Seed has integrated **.npmrc** file and **npm** task in Azure Pipelines.

You need to have in your home directory **.npmrc** file like this:

```bash
@mw:registry=https://pkgs.dev.azure.com/pg-consumer/_packaging/ModernWeb/npm/registry/
@mwrc:registry=https://pkgs.dev.azure.com/pg-consumer/_packaging/MW-reusable-components/npm/registry/

//pkgs.dev.azure.com/pg-consumer/_packaging/ModernWeb/npm/registry/:username=pg-consumer
//pkgs.dev.azure.com/pg-consumer/_packaging/ModernWeb/npm/registry/:_password=[BASE-64 PAT]
//pkgs.dev.azure.com/pg-consumer/_packaging/ModernWeb/npm/registry/:email=[your email]
//pkgs.dev.azure.com/pg-consumer/_packaging/ModernWeb/npm/:username=pg-consumer
//pkgs.dev.azure.com/pg-consumer/_packaging/ModernWeb/npm/:_password=[BASE-64 PAT]
//pkgs.dev.azure.com/pg-consumer/_packaging/ModernWeb/npm/:email=[your email]
//pg-consumer.pkgs.visualstudio.com/_packaging/ModernWeb/npm/registry/:username=pg-consumer
//pg-consumer.pkgs.visualstudio.com/_packaging/ModernWeb/npm/registry/:_password=[BASE-64 PAT]
//pg-consumer.pkgs.visualstudio.com/_packaging/ModernWeb/npm/registry/:email=[your email]
//pg-consumer.pkgs.visualstudio.com/_packaging/ModernWeb/npm/:username=pg-consumer
//pg-consumer.pkgs.visualstudio.com/_packaging/ModernWeb/npm/:_password=[BASE-64 PAT]
//pg-consumer.pkgs.visualstudio.com/_packaging/ModernWeb/npm/:email=[your email]

//pg-consumer.pkgs.visualstudio.com/_packaging/MW-reusable-components/npm/registry/:username=pg-consumer
//pg-consumer.pkgs.visualstudio.com/_packaging/MW-reusable-components/npm/registry/:_password=[BASE-64 PAT]
//pg-consumer.pkgs.visualstudio.com/_packaging/MW-reusable-components/npm/registry/:email=[your email]
//pg-consumer.pkgs.visualstudio.com/_packaging/MW-reusable-components/npm/:username=pg-consumer
//pg-consumer.pkgs.visualstudio.com/_packaging/MW-reusable-components/npm/:_password=[BASE-64 PAT]
//pg-consumer.pkgs.visualstudio.com/_packaging/MW-reusable-components/npm/:email=[your email]
//pkgs.dev.azure.com/pg-consumer/_packaging/MW-reusable-components/npm/registry/:username=pg-consumer
//pkgs.dev.azure.com/pg-consumer/_packaging/MW-reusable-components/npm/registry/:_password=[BASE-64 PAT]
//pkgs.dev.azure.com/pg-consumer/_packaging/MW-reusable-components/npm/registry/:email=[your email]
//pkgs.dev.azure.com/pg-consumer/_packaging/MW-reusable-components/npm/:username=pg-consumer
//pkgs.dev.azure.com/pg-consumer/_packaging/MW-reusable-components/npm/:_password=[BASE-64 PAT]
//pkgs.dev.azure.com/pg-consumer/_packaging/MW-reusable-components/npm/:email=[your email]
```

To get Base-64 PAT you need to run and provided your PAT:

```bash
node -e "require('readline') .createInterface({input:process.stdin,output:process.stdout,historySize:0}) .question('PAT> ',p => { b64=Buffer.from(p.trim()).toString('base64');console.log(b64);process.exit(); })"
```

</details>

---

<details>
<summary><b>I'm getting error "You need the Git 'GenericContribute' permission to perform this action." in production pipeline</b> </summary>

</br>

1. Go to Settings -> Repository.

2. Choose the repository that your pipeline operates on.

3. Select "Project Collection Build Service (pg-consumer)" under Users Security list.

4. Ensure that on Access Control Summary "Allow" is selected next to Contribute access.

</details>

---

<details>
<summary><b>I got a CORS error in the browser console, even if the call returns a 200 status.</b></summary>

</br>

In that case, you'll need to use our [public Search API](https://swiftype.com/documentation/site-search/searching) in order to make requests from the Browser.

</details>

---

<details>
<summary><b>Can I integrate Facebook/Twitter with Janrain, so users don't have to fill all registration fields manual?</b></summary>

</br>

Yes, you can integrate Janrain with all Social Providers listed [here](https://educationcenter.janrain.com/home/identity-providers). Follow this section [TODO link] for more instructions.

</details>

---

<details>
<summary><b>Can I integrate a reference implementation in React as a React component
or the only way is to insert a script tag in the main HTML file</b></summary>

</br>

MW AIC for React is available. Please read [this](https://mw-wiki.pg.com/framework-structure/cg/aic-mw-react-registration-overview).

JS files from the reference implementation can be added to your website's static assets as they are and included in index.html. This is not ideal, but currently the fastest, working solution.

</details>

---

<details>
<summary><b>How can I implement AIC registration via Google Tag Manager?</b></summary>

</br>

Use MW Registration and follow [this guide](https://mw-wiki.pg.com/docs/aic-init-scripts-6VOvFoMABRyTJzXPjGqCyH#embedding-using).

</details>

---

<details>
<summary><b>Do users registered by the AIC registration form provided on the website will be able to use the same credentials on every P&G site?</b></summary>

</br>

No. Every marketing program (MBiB, Pampers, Braun) should have its own AIC flow. This means consumer who registered on Pampers, can't login on Braun website.

</details>

---

<details>
<summary><b>Can I use this component if my browser does not support HLS format at all?</b></summary>

</br>

Yes you can. hls.js library does not need any player. It works on top of HTML video standard. As documentation states:

It works by transmuxing MPEG-2 Transport Stream and AAC/MP3 streams into ISO BMFF (MP4) fragments. This means that it is unlikely it won't work due to popularity of technologies that it uses. But it still might happen. That is why `video.js` library takes other predefined formats that it will serve to user in a situation like this.

</details>

---

<details>
<summary><b>What other examples will be included in future in those repos?</b></summary>

</br>

That's totally up to you. If you'll contact us then [Lingaro Team](https://mw-wiki.pg.com/dictionary?selected=lingaro-team) will reserve some time to provide a solution. We believe that there are many cases in which this kind of approach can be helpful.

</details>

---

<details>
<summary><b>Who should I contact if I want to contribute or provide an interesting me topic?</b></summary>

</br>

Try here [Pawel Trocinski](mailto:trocinski.p@pg.com)

</details>

---

<details>
<summary><b>Do I need to use next.js `withCSS()` config extension to make this work?</b></summary>

</br>

Yes you do. This component uses .css files loaded directly from `video-js` package and unfortunately this requires from us to use this extension within config file.

</details>

---

<details>
<summary><b>Do I have to use implementation provided in a repository?</b></summary>

</br>

No you don't. We are trying to provide an example of how it can be achieved with minimal effort. Those examples are not a required approach in your case.

</details>

---

<details>
<summary><b>What to do if my videos before upload are bigger than 100 MB?</b></summary>

</br>

When you want to serve those videos in HLS or MPEG-DASH format your files need to be uploaded with special parameters that our Contentful media extensions does not support yet. Read more about large files upload here: [How upload files to cloudinary documentation](https://cloudinary.com/documentation/upload_videos)

</details>

---

<details>
<summary><b>Do I need Cloudinary account to use MW Video component?</b></summary>

</br>

The **@mw/video** component doesn't require Cloudinary account, although it require the served video to be hosted on Cloudinary. The only exception is that files bigger than 100MB need to be uploaded directly to Cloudinary with `eager transformation` parameter.

</details>

---

<details>
<summary><b>Do I have to use this package as a video player?</b></summary>

</br>

That depends. If your video content is not a crucial part of your project, e.g: background video or some banner displaying visuals, then we encourage you to do so. That's why it's already integrated into [MW-Seed](https://pg-consumer.visualstudio.com/MW-Framework/_git/MW-seed). Otherwise, you will need to implement [Youtube Player API](https://developers.google.com/youtube/iframe_api_reference) because accessibility standard will require to upload subtitles and it seams to be easier solution.

</details>

---

<details>
<summary><b>Select *Azure Repos Git*</b></summary>

</br>

![](../images/setup_pipelines2.webp)

</details>

---

<details>
<summary><b>Go to your project's pipelines > New Pipeline</b></summary>

</br>

![](../images/setup_pipelines1.webp)

</details>

---

<details>
<summary><b>Requirements say, all complex logic should be moved out from the components. What about methods that change component's internal state, dynamic className setting based on props or destructuring from props?</b></summary>

</br>

All above operations can be part of a component class / function. The good rule of thumb is, that if changing internal state or dynamic classNames requires more than a single "**conditional statement**", "**and**" or "**or**" operator, or any mix of them, then the logic code should be moved out in form of **pure function**, tested and imported inside the component to use.

</details>

---

<details>
<summary><b>I can't see nor access to the "Repos" section.</b></summary>

</br>

If you can access the above space but you can't see the repository section, you are probably on a **STAKEHOLDER** license. In order to upgrade it to **BASIC**, make use of [SNOW](https://pgglobalenterprise.service-now.com/dbce_homepage?id=cshomepage) ticketing system.

1. Go to - Hosting -> Request Access.

2. Fill the form.

   - Choose - Create New Access/ DevOps Access

   - Select "Basic" as a License

**Notes:** Inactivity longer then 2 months

In case of inactivity longer than 2 months, your account is going to be downgraded automatically.

</details>

---

<details>
<summary><b>Do we need a commercial account for Youtube to avoid advertisements?</b></summary>

</br>

No, we don't.

Advertisements are displayed on videos uploaded by free accounts only for the author's request or in [case of a content rights violation](https://support.google.com/adsense/answer/2542482?hl=en&ref_topic=1250107).

</details>

---

<details>
<summary><b>What YT account should I use?</b></summary>

</br>

DDAs often must work without dependency from the brand manager, therefore be independent in their ability to upload and share the video.

For this reason, to upload videos to YT we recommend either:

- Using the brand's YT channel if direct access is possible

- Using DDA's YT account created for the purpose of a particular website otherwise

</details>

---

<details>
<summary><b>Who is a Product Owner at P&G?</b></summary>

</br>

Contentful contract and relationship is maintained by Digital Brand & Consumer Experiences.

Contact: [Marcin Pacyga](mailto:pacyga.m@pg.com)

</details>

---

<details>
<summary><b>How to upgrade to another tier?</b></summary>

</br>

Contact [Dominika Forgalska](forgalska.f@pg.com)

</details>

---

<details>
<summary><b>How to raise a problem?</b></summary>

</br>

User Management, Contentful access related issues: Dominika Forgalska Platform availability:

- Contentful status page: https://www.contentfulstatus.com/

- Ping services availability, P&G account problems: gethelp@pg.com

- Urgent serious problems / errors; contact Contentful support directly: https://www.contentful.com/support/ (quoting organization ID: 5i0sA6kihMnpqixItAwL0c)

- Non-urgent problems: pacyga.m@pg.com

</details>

---

<details>
<summary><b>How to request guidance on Contentful Project?</b></summary>

</br>

1. Via teams channel (see links)

2. P&G Expert: Marcin Pacyga (pacyga.m@pg.com)

3. Technical Account Services for Contentful are available. Requested by and per project - contact Marcin for current offer with rates.

4. [Contentful Community](https://www.contentfulcommunity.com/), login via PG account if created in Contentful

</details>

---

<details>
<summary><b>How to request new space in Contentful?</b></summary>

</br>

In order to create a new Contentful space a user must create a request via Modern Web Inventory. New Contentful space can be requested via a new or existing records. To do so user should:

1. Open a new [MWI](https://webapp-mwi.pg.com/) record or select edit on existing record

2. Go to Contentful section

3. Input new Contentful Space name and select the add button

4. Provide Space owner (must be a @pg email) and space admin

5. Select save

After completing the above the Contentful space is in Requested status. Next the App admin will review the request and provide approval or reject. If approval is granted the space will be created automatically. User can see the space status will change to "Existing" both in All Approved tab and the assigned record. This will indicate the process is complete.

</details>

---

<details>
<summary><b>How to request access to Contentful?</b></summary>

</br>

In order to access Contentful user needs to be part of Azure group: GBSG-ConsumerSolutions-ContentfulUsers

To get added to group please email [Mateusz Drobik](drobik.m@pg.com). In the email provide your PG ID and space name you want to be part of.

User can log in to Contentful via SSO. Detailed instruction for SSO login below.

[Download Contentful SSO log in instruction.pdf](https://assets.ctfassets.net/0ugnex1a33i6/6gTVSzvjccDiJgayLY3Wn/1f81add03a0a05824dc1832a33b9165b/Contentful_SSO_log_in_instruction.pdf) Once user is added to azure group Space admin(s) can grant access to space.

</details>

---

<details>
<summary><b>Can I use MW Image component for background images?</b></summary>

</br>

Yes. The image is rendered as a background image automatically if the **MW Image** component receives any **children** (using render props pattern).

Your user will enjoy the same optimizations.

</details>

---

<details>

<summary><b>Does it automatically fetch images in the best format?</b></summary>

</br>

Yes, it does.

</details>

---

<details>
<summary><b>Do I need Cloudinary account to use MW Image component with Cloudinary?</b></summary>

</br>

The MW Image component doesn't require Cloudinary account, although it requires images to be hosted on Cloudinary.

It utilizes the Cloudinary dynamic transformations, so the content editor can upload the high-res image , and users will receive the optimized version on every device.

</details>

---

<details>
<summary><b>Does it fetch 2x and 3x images for Retina displays?</b></summary>

</br>

We've tried this approach and decided to drop it because multiple flaws discovered e.g. when Macbook user browse the website using external Full HD monitor, the browser claims he is using retina, and therefore he gets 2-3 times bigger images than his monitor can display.

Also, some devices have 4 times bigger pixel density, and therefore we would serve them 4k images (20mb) on mobile, what doesn't seem right, and we doubt that this could have more positive than negative UX influence.

</details>
