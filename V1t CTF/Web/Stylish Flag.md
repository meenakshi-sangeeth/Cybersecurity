## Challenge

Are you a front end dev?
https://tommytheduck.github.io/stylish_flag/

## Solution

```bash
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <title>Stylish Flag</title>
  <link rel="stylesheet" href="csss.css">
</head>

<body>
  <h1>where is the flag ;-;</h1>
  <br>
  <div hidden class="flag"></div>
</body>

</html>
```

```bash
        body {
        background: #111;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
    }

    h1 {
        font-size: 100px;
        color: #0f0;
    }

    .flag {
        width: 8px;
        height: 8px;
        background: #0f0;
        transform: rotate(180deg);
        opacity: 0.05;
        box-shadow:
            264px 0px #0f0,
            1200px 0px #0f0,
            0px 8px #0f0,
            32px 8px #0f0,
            88px 8px #0f0,
            96px 8px #0f0,
            160px 8px #0f0,
            168px 8px #0f0,
            176px 8px #0f0,
            184px 8px #0f0,
            192px 8px #0f0,
            256px 8px #0f0,
            320px 8px #0f0,
            344px 8px #0f0,
            408px 8px #0f0,
            416px 8px #0f0,
            480px 8px #0f0,
            488px 8px #0f0,
            496px 8px #0f0,
            560px 8px #0f0,
            568px 8px #0f0,
            576px 8px #0f0,
            640px 8px #0f0,
            648px 8px #0f0,
            656px 8px #0f0,
            712px 8px #0f0,
            720px 8px #0f0,
            736px 8px #0f0,
            744px 8px #0f0,
            792px 8px #0f0,
            800px 8px #0f0,
            808px 8px #0f0,
            816px 8px #0f0,
            824px 8px #0f0,
            960px 8px #0f0,
            968px 8px #0f0,
            976px 8px #0f0,
            1040px 8px #0f0,
            1048px 8px #0f0,
            1056px 8px #0f0,
            1112px 8px #0f0,
            1120px 8px #0f0,
            1128px 8px #0f0,
            1136px 8px #0f0,
            1200px 8px #0f0,
            1208px 8px #0f0,
            0px 16px #0f0,
            8px 16px #0f0,
            24px 16px #0f0,
            32px 16px #0f0,
            80px 16px #0f0,
            88px 16px #0f0,
            96px 16px #0f0,
            104px 16px #0f0,
            168px 16px #0f0,
            176px 16px #0f0,
            248px 16px #0f0,
            256px 16px #0f0,
            320px 16px #0f0,
            344px 16px #0f0,
            400px 16px #0f0,
            408px 16px #0f0,
            416px 16px #0f0,
            480px 16px #0f0,
            504px 16px #0f0,
            576px 16px #0f0,
            584px 16px #0f0,
            640px 16px #0f0,
            656px 16px #0f0,
            664px 16px #0f0,
            712px 16px #0f0,
            720px 16px #0f0,
            736px 16px #0f0,
            744px 16px #0f0,
            808px 16px #0f0,
            952px 16px #0f0,
            960px 16px #0f0,
            1032px 16px #0f0,
            1040px 16px #0f0,
            1112px 16px #0f0,
            1200px 16px #0f0,
            1208px 16px #0f0,
            0px 24px #0f0,
            8px 24px #0f0,
            24px 24px #0f0,
            32px 24px #0f0,
            96px 24px #0f0,
            104px 24px #0f0,
            168px 24px #0f0,
            176px 24px #0f0,
            248px 24px #0f0,
            256px 24px #0f0,
            320px 24px #0f0,
            328px 24px #0f0,
            336px 24px #0f0,
            344px 24px #0f0,
            408px 24px #0f0,
            416px 24px #0f0,
            480px 24px #0f0,
            504px 24px #0f0,
            576px 24px #0f0,
            632px 24px #0f0,
            640px 24px #0f0,
            656px 24px #0f0,
            664px 24px #0f0,
            712px 24px #0f0,
            720px 24px #0f0,
            736px 24px #0f0,
            744px 24px #0f0,
            808px 24px #0f0,
            952px 24px #0f0,
            1032px 24px #0f0,
            1040px 24px #0f0,
            1112px 24px #0f0,
            1120px 24px #0f0,
            1200px 24px #0f0,
            1208px 24px #0f0,
            8px 32px #0f0,
            24px 32px #0f0,
            96px 32px #0f0,
            104px 32px #0f0,
            168px 32px #0f0,
            176px 32px #0f0,
            240px 32px #0f0,
            248px 32px #0f0,
            320px 32px #0f0,
            328px 32px #0f0,
            336px 32px #0f0,
            344px 32px #0f0,
            408px 32px #0f0,
            416px 32px #0f0,
            480px 32px #0f0,
            504px 32px #0f0,
            568px 32px #0f0,
            576px 32px #0f0,
            584px 32px #0f0,
            632px 32px #0f0,
            640px 32px #0f0,
            648px 32px #0f0,
            664px 32px #0f0,
            712px 32px #0f0,
            720px 32px #0f0,
            736px 32px #0f0,
            744px 32px #0f0,
            808px 32px #0f0,
            952px 32px #0f0,
            1048px 32px #0f0,
            1056px 32px #0f0,
            1120px 32px #0f0,
            1128px 32px #0f0,
            1136px 32px #0f0,
            1208px 32px #0f0,
            1216px 32px #0f0,
            8px 40px #0f0,
            16px 40px #0f0,
            24px 40px #0f0,
            96px 40px #0f0,
            104px 40px #0f0,
            168px 40px #0f0,
            176px 40px #0f0,
            248px 40px #0f0,
            256px 40px #0f0,
            320px 40px #0f0,
            344px 40px #0f0,
            408px 40px #0f0,
            416px 40px #0f0,
            480px 40px #0f0,
            504px 40px #0f0,
            576px 40px #0f0,
            584px 40px #0f0,
            640px 40px #0f0,
            664px 40px #0f0,
            712px 40px #0f0,
            720px 40px #0f0,
            736px 40px #0f0,
            744px 40px #0f0,
            808px 40px #0f0,
            952px 40px #0f0,
            960px 40px #0f0,
            1056px 40px #0f0,
            1064px 40px #0f0,
            1136px 40px #0f0,
            1200px 40px #0f0,
            1208px 40px #0f0,
            8px 48px #0f0,
            16px 48px #0f0,
            24px 48px #0f0,
            88px 48px #0f0,
            96px 48px #0f0,
            104px 48px #0f0,
            112px 48px #0f0,
            168px 48px #0f0,
            176px 48px #0f0,
            248px 48px #0f0,
            256px 48px #0f0,
            320px 48px #0f0,
            344px 48px #0f0,
            400px 48px #0f0,
            408px 48px #0f0,
            416px 48px #0f0,
            424px 48px #0f0,
            480px 48px #0f0,
            488px 48px #0f0,
            496px 48px #0f0,
            560px 48px #0f0,
            568px 48px #0f0,
            576px 48px #0f0,
            640px 48px #0f0,
            648px 48px #0f0,
            656px 48px #0f0,
            664px 48px #0f0,
            720px 48px #0f0,
            728px 48px #0f0,
            736px 48px #0f0,
            808px 48px #0f0,
            960px 48px #0f0,
            968px 48px #0f0,
            976px 48px #0f0,
            1032px 48px #0f0,
            1040px 48px #0f0,
            1048px 48px #0f0,
            1056px 48px #0f0,
            1112px 48px #0f0,
            1120px 48px #0f0,
            1128px 48px #0f0,
            1136px 48px #0f0,
            1200px 48px #0f0,
            1208px 48px #0f0,
            248px 56px #0f0,
            256px 56px #0f0,
            1200px 56px #0f0,
            1208px 56px #0f0,
            256px 64px #0f0,
            264px 64px #0f0,
            872px 64px #0f0,
            880px 64px #0f0,
            888px 64px #0f0,
            896px 64px #0f0,
            904px 64px #0f0,
            1192px 64px #0f0,
            1200px 64px #0f0;
    }
```

The flag was rendered as pixel art using CSS box-shadow. Made the following changes to view the flag
- removed "hidden" from `<div hidden class="flag"></div>`
- removed "where is the flag ;-;" from `<h1>where is the flag ;-;</h1>`
- increased the opacity to 1
- removed `transform: rotate(180deg);`

<img width="1302" height="866" alt="image" src="https://github.com/user-attachments/assets/7b30dedf-415c-4812-88a4-59c3032a945a" />

Flag: `v1t{H1D30UT_ CSS}`


