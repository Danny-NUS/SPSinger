## Abstract of the paper

<div style="text-align: justify">
Current singing voice synthesis systems often struggle in multi-singer scenarios due to limited training data that only includes a few singers. Existing zero-shot multi-singer singing voice synthesis systems are criticized for their reliance on global timbre embeddings from single reference audio, which fail to capture sufficient timbre details. This paper introduces SPSinger, a multi-singer singing voice synthesizer that generates singer-specific voices from brief reference audio (around \textit{5 seconds}) without prior training on the singer's voice. 
SPSinger builds on the StableDiffusion framework by adding a global encoder to capture consistent timbre features from short reference prompts and an attention-based local encoder to capture detailed variations from long prompts, used only during training. 
To overcome the challenge of requiring long audio prompts during inference, we introduce the Latent Prompt Adaptation Model (LPAM), a Transformer-based module that derives timbre features from global embeddings. This approach eliminates the need for long reference prompts. Additionally, we propose a novel pitch shift algorithm that uses LPAM to predict the pitch shift values.
Our experiments show that SPSinger achieves high-quality singing voice synthesis that preserves the identity of the target singer, even when using only short reference audio inputs in zero-shot scenarios.
</div>

<p></p>
<div style="text-align: center;">
    <img src="SPSinger_overall.png" width="1000px">
    <figcaption>Fig.1 Overall Architecture of SPSinger.</figcaption>
</div>

## Synthesis Results on Seen Singers
<br>
<table>
    <thead>
        <tr>
            <th colspan="4">Synthesis on Seen Singers with Short Music Scores</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><center>Singers</center></td>
            <td><center>GT mel + Vocoder</center></td>
            <td><center>Reference</center></td>
            <td><center>SPSinger</center></td>
        </tr>
        <tr>
            <td>Female Singer 0</td>
            <td>
                <audio controls>
                  <source src="short_seen/female_0_short_seen/groud_truth.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                  </audio>
            </td>
            <td>
                <audio controls>
                  <source src="short_seen/female_0_short_seen/reference.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="short_seen/female_0_short_seen/spsinger.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>Female Singer 1</td>
            <td>
                <audio controls>
                  <source src="short_seen/female_1_short_seen/groud_truth.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                  </audio>
            </td>
            <td>
                <audio controls>
                  <source src="short_seen/female_1_short_seen/reference.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="short_seen/female_1_short_seen/spsinger.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>Female Singer 2</td>
            <td>
                <audio controls>
                  <source src="short_seen/female_2_short_seen/groud_truth.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                  </audio>
            </td>
            <td>
                <audio controls>
                  <source src="short_seen/female_2_short_seen/reference.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="short_seen/female_2_short_seen/spsinger.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>Male Singer 0</td>
            <td>
                <audio controls>
                  <source src="short_seen/male_0_short_seen/groud_truth.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                  </audio>
            </td>
            <td>
                <audio controls>
                  <source src="short_seen/male_0_short_seen/reference.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="short_seen/male_0_short_seen/spsinger.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>Male Singer 1</td>
            <td>
                <audio controls>
                  <source src="short_seen/male_1_short_seen/groud_truth.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                  </audio>
            </td>
            <td>
                <audio controls>
                  <source src="short_seen/male_1_short_seen/reference.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="short_seen/male_1_short_seen/spsinger.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>Male Singer 2</td>
            <td>
                <audio controls>
                  <source src="short_seen/male_2_short_seen/groud_truth.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                  </audio>
            </td>
            <td>
                <audio controls>
                  <source src="short_seen/male_2_short_seen/reference.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="short_seen/male_2_short_seen/spsinger.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
    </tbody>
    <thead>
        <tr>
            <th colspan="4">Synthesis on Seen Singers with Long Music Scores</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><center>Singers</center></td>
            <td><center>GT mel + Vocoder</center></td>
            <td><center>Reference</center></td>
            <td><center>SPSinger</center></td>
        </tr>
        <tr>
            <td>Female Singer 0</td>
            <td>
                <audio controls>
                  <source src="short_unseen/female_0_short_unseen/groud_truth.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                  </audio>
            </td>
            <td>
                <audio controls>
                  <source src="short_unseen/female_0_short_unseen/reference.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="short_unseen/female_0_short_unseen/spsinger.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>Female Singer 1</td>
            <td>
                <audio controls>
                  <source src="short_unseen/female_1_short_unseen/groud_truth.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                  </audio>
            </td>
            <td>
                <audio controls>
                  <source src="short_unseen/female_1_short_unseen/reference.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="short_unseen/female_1_short_unseen/spsinger.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>Female Singer 2</td>
            <td>
                <audio controls>
                  <source src="short_unseen/female_2_short_unseen/groud_truth.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                  </audio>
            </td>
            <td>
                <audio controls>
                  <source src="short_unseen/female_2_short_unseen/reference.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="short_unseen/female_2_short_unseen/spsinger.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>Male Singer 0</td>
            <td>
                <audio controls>
                  <source src="short_unseen/male_0_short_unseen/groud_truth.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                  </audio>
            </td>
            <td>
                <audio controls>
                  <source src="short_unseen/male_0_short_unseen/reference.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="short_unseen/male_0_short_unseen/spsinger.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>Male Singer 1</td>
            <td>
                <audio controls>
                  <source src="short_unseen/male_1_short_unseen/groud_truth.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                  </audio>
            </td>
            <td>
                <audio controls>
                  <source src="short_unseen/male_1_short_unseen/reference.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="short_unseen/male_1_short_unseen/spsinger.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>Male Singer 2</td>
            <td>
                <audio controls>
                  <source src="short_unseen/male_2_short_unseen/groud_truth.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                  </audio>
            </td>
            <td>
                <audio controls>
                  <source src="short_unseen/male_2_short_unseen/reference.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="short_unseen/male_2_short_unseen/spsinger.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
    </tbody>
</table>

## Data Acquirement
<div style="text-align: justify">
If you want the manual singing technique annotation file for opencpop dataset, access <a href="https://docs.google.com/spreadsheets/d/1p1BRTCmCrcLdBm28w3OfeZ6mK3E752rD/edit?usp=drive_link&ouid=109505594792565231495&rtpof=true&sd=true">here</a> and request a permission. The annotation is research purpose only.
</div>
<div style="text-align: justify">
The request should include the following. Otherwise it will be rejected.
<ul>
    <li>Name</li>
    <li>Affiliation</li>
    <li>Email Address</li>
    <li>Agree to the <a href="#license">License</a></li>
</ul>
</div>
<div style="text-align: justify">
For Opencpop dataset: Please trictly follow the instructions of <a href="https://wenet.org.cn/opencpop/">Opencpop</a>. We have no right to give you the access to Opencpop.
</div>

## Annotated Data Statistics
<ul>
<li>Distribution of manually annotated portion of Opencpop dataset. (The singing techniques "whisper" and "hiccup" are removed due to the small amount of labels.) </li>
<div style="text-align: center;">
    <img src="dataset.png" width="450px">
</div>
<li>Distribution of duration of each singing technique.</li>
<div style="text-align: center;">
    <img src="violin.png" width="800px">
</div>
</ul>


## SinTechSVS Samples

### Singing Voice Synthesis with Singing Technique Control
<div style="text-align: justify">
    In this section, we provide synthesized samples of SinTechSVS conditioned on singing techniques. In <b>Word-level Lyric Sequence</b>, bolded words are sung in the specific technique. <b>Regular/Straight</b> denotes synthesized audio with no singing techniques, serving as a reference for comparison.
</div>
<br>
<table>
    <thead>
        <tr>
            <th colspan="4">SinTechSVS Synthesized Samples Conditioned on Pitch Singing Techniques</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><center>Pitch Singing Techniques</center></td>
            <td><center><div style="width: 170pt"> Word-level Lyric Sequence</div></center></td>
            <td><center>Regular/Straight</center></td>
            <td><center>SinTechSVS</center></td>
        </tr>
        <tr>
            <td>Scooping</td>
            <td>
                <center>
                    冰 刀 <span style="text-decoration: underline; font-weight: bold; color: red;"> 划 </span> 的 圈
                    <br>
                    bing dao <span style="text-decoration: underline; font-weight: bold; color: red;">hua</span> de quan
                </center>
            </td>
            <td>
                <audio controls>
                  <source src="scooping_regular.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="scooping.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>Bend</td>
            <td>
                <center>
                    又 无 可 <span style="text-decoration: underline; font-weight: bold; color: red;">奈</span> 何
                    <br>
                    you wu ke <span style="text-decoration: underline; font-weight: bold; color: red;">nai</span> he
                </center>
            </td>
            <td>
                <audio controls>
                  <source src="bending_regular.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="bending.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>Drop</td>
            <td>
                <center>
                    小 火 车  摆 <span style="text-decoration: underline; font-weight: bold; color: red;">动</span> 的 旋 律
                    <br>
                    xiao huo che  bai <span style="text-decoration: underline; font-weight: bold; color: red;">dong</span> de xuan lv
                </center>
            </td>
            <td>
                <audio controls>
                  <source src="drop_regular.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="drop.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>Melisma</td>
            <td>
                <center>
                    你 在 世 俗 里 的 名 字 被 人 用 <span style="text-decoration: underline; font-weight: bold; color: red;">了</span>
                    <br>
                    ni zai shi su li de ming zi bei ren yong <span style="text-decoration: underline; font-weight: bold; color: red;">le</span>
                </center>
            </td>
            <td>
                <audio controls>
                  <source src="melisma_regular.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="melisma.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
    </tbody>
    <thead>
        <tr>
            <th colspan="4">SinTechSVS Synthesized Samples Conditioned on Timbre Singing Techniques</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Vocal Fry</td>
            <td>
                <center>
                    <span style="text-decoration: underline; font-weight: bold; color: red;">喔 喔</span>
                    <br>
                    <span style="text-decoration: underline; font-weight: bold; color: red;">wo wo</span>
                </center>
            </td>
            <td>
                <audio controls>
                  <source src="vocalfry_regular.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="vocalfry.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>Falsetto</td>
            <td>
                <center>
                    <span style="text-decoration: underline; font-weight: bold; color: red;">我 恨 你</span>
                    <br>
                    <span style="text-decoration: underline; font-weight: bold; color: red;">wo hen ni</span>
                </center>
            </td>
            <td>
                <audio controls>
                  <source src="falsetto_regular.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="falsetto.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>Breathy</td>
            <td>
                <center>
                    <span style="text-decoration: underline; font-weight: bold; color: red;">很 少 人 看 诗</span>
                    <br>
                    <span style="text-decoration: underline; font-weight: bold; color: red;">hen shao ren kan shi</span>
                </center>
            </td>
            <td>
                <audio controls>
                  <source src="breathy_regular.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="breathy.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>Belting</td>
            <td>
                <center>
                    <span style="text-decoration: underline; font-weight: bold; color: red;">你 好 吗</span>
                    <br>
                    <span style="text-decoration: underline; font-weight: bold; color: red;">ni hao ma</span>
                </center>
            </td>
            <td>
                <audio controls>
                  <source src="belting_regular.wav" type="audio/mpeg", style="display: inline;">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
               <audio controls>
                  <source src="belting.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
    </tbody>
</table>

### Singing Voice Synthesis with Singing Technique Recommendation
 <script type="text/javascript" src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=AM_HTMLorMML-full"></script>
<div style="text-align: justify">
    In this section, we provide synthesized samples of SinTechSVS conditioned on singing techniques recommended from the music score. <b>STan</b> represents SinTechSVS with annotated singing technique labels. <b>SinTechSVS</b> use the STR to predict the singing techniques for input.
</div>
<br>
<table>
    <thead>
        <tr>
            <th colspan="3">SinTechSVS Synthesized Samples Conditioned on Recommended Singing Techniques</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><center>Ground Truth</center></td>
            <td><center>STan</center></td>
            <td><center>SinTechSVS</center></td>
        </tr>
        <tr>
            <td>
                <audio controls>
                  <source src="GT/2099003684.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="STan/2099003684.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="SinTechSVS_/2099003684.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>
                <audio controls>
                  <source src="GT/2086003182.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="STan/2086003182.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="SinTechSVS_/2086003182.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>
                <audio controls>
                  <source src="GT/2081002987.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="STan/2081002987.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="SinTechSVS_/2081002987.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>
                <audio controls>
                  <source src="GT/2072002678.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="STan/2072002678.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="SinTechSVS_/2072002678.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>
                <audio controls>
                  <source src="GT/2046001741.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="STan/2046001741.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="SinTechSVS_/2046001741.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
    </tbody>
</table>

### Singing Voice Synthesis with Singing Technique Recommendation (Unseen)

<div style="text-align: justify">
This section showcases singing technique recommendations through unseen music score samples and their corresponding synthesized audio demonstrations. For pitch singing techniques, the abbreviations are: (1) straight - <b>STR</b>; (2) scooping - <b>SCO</b>; (3) bend - <b>BEND</b>; (4) drop - <b>DROP</b>; (5) melisma - <b>MEL</b>. For timbre singing techniques, the abbreviations are: (1) regular - <b>REG</b>; (2) vocal fry - <b>FRY</b>; (3) falsetto - <b>FAL</b>; (4) breathy: <b>BRE</b>; (5) belting: <b>BEL</b>. The word-level pitch, lyric, slur, and singing technique will be separated by |.
</div>

<br>
<table>
    <thead>
        <tr>
            <th colspan="2">Unseen Sample 1</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>
                <center><div style="width: 100pt">Input Sequence</div></center>
            </td>
            <td>
                <div style="width: 630pt"> <center>Lyrics: 但(dan) | 我(wo) | 早(zao) | 已(yi) | 学(xue) | 会(hui) | 一(yi) | 个(ge) | 人(ren) | 想(xiang) | 你(ni) </center>
                <center>Pitch: A3 | F#4/Gb4 E4 D4 | F#4/Gb4 | B4 | C#5/Db5 | B4 | A4 | F#4/Gb4 | E4 | D4 | F#4/Gb4 E4 D4</center>
                <center>Slur: 0 | 0 | 0 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 1 | 0 | 0 | 0 | 1
                </center>
                </div>
            </td>
        </tr>
        <tr>
            <td>
                <center>Output Pitch Singing Techniques</center>
            </td>
            <td>
                <center>STR | MEL | REG | REG | SCO | REG | REG | DROP | REG | REG | MEL </center>
            </td>
        </tr>
        <tr>
            <td>
                <center>Output Timber Singing Techniques</center>
            </td>
            <td>
                <center>REG | BEL | BEL | FAL | FAL | FAL | FAL | BRE | BRE | REG | BRE</center>
            </td>
        </tr>
        <tr>
            <td>
                <center>Synthesized Audio</center>
            </td>
            <td>
                <center>
                <audio controls>
                  <source src="unseen1.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
                </center>
            </td>
        </tr>
    </tbody>
</table>

<table>
    <thead>
        <tr>
            <th colspan="2">Unseen Sample 2</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>
                <center><div style="width: 100pt">Input Sequence</div></center>
            </td>
            <td>
                <div style="width: 630pt"> <center>Lyrics: 看(kan) | 着(zhe) | 我(wo) | 的(de) | 脚(jiao) | 印(yin) | 一(yi) | 个(ge) | 人(ren) | 一(yi) | 步(bu) | 步(bu) | 好(hao) | 寂(ji) | 寞(mo)
                </center>
                <center>Pitch: F4 | G4 | E4 | D4 | C4 | D4 C4 A4 | E4 | F4 | C5 | E4 | F4 | C5 | E4 | F4 | F4
                </center>
                <center>Slur: 0 | 0 | 0 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 1 | 0 | 0 | 0 | 1
                </center>
                </div>
            </td>
        </tr>
        <tr>
            <td>
                <center>Output Pitch Singing Techniques</center>
            </td>
            <td>
                <center>STR | STR | SCO | STR | REG | MEL | STR | STR | SCO | STR | STR | SCO | STR | STR | SCO
                </center>
            </td>
        </tr>
        <tr>
            <td>
                <center>Output Timber Singing Techniques</center>
            </td>
            <td>
                <center>BEL | BEL | BEL | BEL | BEL | REG | REG | REG | FAL | REG | REG | FAL | REG | REG | BEL
                </center>
            </td>
        </tr>
        <tr>
            <td>
                <center>Synthesized Audio</center>
            </td>
            <td>
                <center>
                <audio controls>
                  <source src="unseen2.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
                </center>
            </td>
        </tr>
    </tbody>
</table>

<table>
    <thead>
        <tr>
            <th colspan="2">Unseen Sample 3</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>
                <center><div style="width: 100pt">Input Sequence</div></center>
            </td>
            <td>
                <div style="width: 630pt"> <center>Lyrics: 有(you) | 什(shen) | 么(me) | 方(fang) | 法(fa) | 让(rang) | 自(zi) | 己(ji) | 真(zhen) | 的(de) | 忘(wang) | 记 (ji) | ha | ha
                 </center>
                <center>Pitch: G4 | A4 | A#4/Bb4 | A4 F4 | C4 | A#4/Bb4 | A4 | F4 | A#4/Bb4 | A4 | A#4/Bb4 | C5 | A#4/Bb4 A4 | A4 G4 F4
                </center>
                <center>Slur: 0 | 0 | 0 | 0 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 1 | 0 | 1
                </center>
                </div>
            </td>
        </tr>
        <tr>
            <td>
                <center>Output Pitch Singing Techniques</center>
            </td>
            <td>
                <center>STR | STR | SCO | BEND | BEND | STR | STR | STR | BEND | STR | STR | SCO | DROP | MEL
                </center>
            </td>
        </tr>
        <tr>
            <td>
                <center>Output Timber Singing Techniques</center>
            </td>
            <td>
                <center>REG | REG | REG | BRE | BRE | BEL | BEL | BEL | BRE | BRE | BRE | FAL | BRE | BRE
                </center>
            </td>
        </tr>
        <tr>
            <td>
                <center>Synthesized Audio</center>
            </td>
            <td>
                <center>
                <audio controls>
                  <source src="unseen3.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
                </center>
            </td>
        </tr>
    </tbody>
</table>

## Citation 
Cite the IEEE/ACM Transactions on Audio, Speech, and Language Processing journal paper.
```
@ARTICLE{10509739,
  author={Zhao, Junchuan and Chetwin, Low Qi Hong and Wang, Ye},
  journal={IEEE/ACM Transactions on Audio, Speech, and Language Processing}, 
  title={SinTechSVS: A Singing Technique Controllable Singing Voice Synthesis System}, 
  year={2024},
  volume={},
  number={},
  pages={1-13},
  keywords={Hidden Markov models;Annotations;Timbre;Task analysis;Deep learning;Synthesizers;Controllability;Singing voice synthesis;singing voice synthesis conditioned on singing techniques;singing technique classification;singing technique recommendation;metric;deep learning},
  doi={10.1109/TASLP.2024.3394769}
}
```

## Contact
If you have any questions about the paper, please contact the first author Junchuan by junchuan@comp.nus.edu.sg.

<a id="license"></a>
## License
<ul>
<li><div style="text-align: justify">
The singing technique annotation for Opencpop is available to download for non-commercial purposes under the <a href="https://wenet.org.cn/opencpop/liscense/">Opencpop license</a>. 
</div>
</li>
<li>
<div style="text-align: justify">
This annotation may not be sold, leased, published or distributed to any third party without written permission from the administrator.
</div>
</li>
<li>
<div style="text-align: justify">
The National University of Singapore is not responsible for errors in the annotation's content or any damages resulting from its use. The administrator may update these conditions of use at any time.
</div>
</li>
</ul>


