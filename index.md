
<html lang="en-US">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <meta name="theme-color" content="#157878">
    <link rel="stylesheet" href="/assets/css/style.css?v=e27bf585b9c641a881074e09853cb11204774c97">
  </head>
  <body>


<h2>0. Contents</h2>
<ol>
  <li><a href="#abstract">Abstract</a></li>
  <li><a href="#samples-comp">Synthesized samples – Comparison with other models</a></li>
  <li><a href="#samples-rf">Synthesized samples – Fixed reduction factors</a></li>
  <li><a href="#samples-mask">synthesized samples – W/ V.S. W/O causality mask</a></li>
  <li><a href="#alignments">Attention alignemnt convergence dynamics</a></li>
  <li><a href="#others">Other results</a></li>
</ol>

<h2>1. Abstract<a name="abstract"></a></h2>

<p>This paper describes a variational auto-encoder based non-autoregressive text-to-speech (VAENAR-TTS) model. The autoregressive TTS (AR-TTS) models based on the sequence-to-sequence architecture can generate high-quality speech, but their sequential decoding process can be time-consuming. Recently, non-autoregressive TTS (NAR-TTS) models have been shown to be more efficient with the parallel decoding process. However, these NAR-TTS models rely on phoneme-level durations to generate a hard alignment between the text and the spectrogram. Obtaining duration labels, either through force-alignment or knowledge distillation, is cumbersome. Furthermore, hard alignment based on phoneme expansion can degrade the naturalness of the synthesized speech. In contrast, the proposed model of VAENAR-TTS is an end-to-end approach that does not require phoneme-level duration. VAENAR-TTS model does not contain recurrent structures and is completely non-autoregressive in both the training and inference phase. Based on the VAE architecture, the alignment information is encoded in the latent variable, and the attention-based soft alignment between the text and the latent variable is used in the decoder to reconstruct the spectrogram. Experiments show that VAENAR-TTS achieves state-of-the-art synthesis quality, while the synthesis speed is comparable with other NAR-TTS models.</p>

<p>Source Codes will be released soon!</p>

<h2>3. Synthesized samples -- Comparison with other models<a name="samples-comp"></a></h2>

<h3>Below lists the samples that are synthesized for the subjective evaluation.</h3>

<p>LJ003-0305. The provision of more baths was also suggested, and the daily sweeping out of the prison.</p>

<table>
  <thead>
    <tr>
      <th style="text-align: left"><strong>BVAE-TTS</strong></th>
      <th style="text-align: left"><strong>FastSpeech2</strong></th>
      <th style="text-align: left"><strong>Glow-TTS</strong></th>
      <th style="text-align: left"><strong>Tacotron 2</strong></th>
      <th style="text-align: left"><strong>VAENAR-TTS (ours)</strong></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align: left"><audio src="wavs\4.BVAE-TTS\LJ003-0305.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\5.FastSpeech2\LJ003-0305.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\3.Glow-TTS\LJ003-0305.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\2.Tacotron2\LJ003-0305.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\6.VAENAR-TTS\LJ003-0305.wav" controls="" preload=""></audio></td>
    </tr>
  </tbody>
</table>

<p>LJ009-0046. But the attempt fails; he trembles, his knees knock together, and his head droops as he enters the condemned pew.</p>

<table>
  <thead>
    <tr>
      <th style="text-align: left"><strong>BVAE-TTS</strong></th>
      <th style="text-align: left"><strong>FastSpeech2</strong></th>
      <th style="text-align: left"><strong>Glow-TTS</strong></th>
      <th style="text-align: left"><strong>Tacotron 2</strong></th>
      <th style="text-align: left"><strong>VAENAR-TTS (ours)</strong></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align: left"><audio src="wavs\4.BVAE-TTS\LJ009-0046.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\5.FastSpeech2\LJ009-0046.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\3.Glow-TTS\LJ009-0046.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\2.Tacotron2\LJ009-0046.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\6.VAENAR-TTS\LJ009-0046.wav" controls="" preload=""></audio></td>
    </tr>
  </tbody>
</table>

<p>LJ005-0100. For this purpose it kept up an extensive correspondence with all parts of the kingdom, and circulated queries to be answered in detail,</p>

<table>
  <thead>
    <tr>
      <th style="text-align: left"><strong>BVAE-TTS</strong></th>
      <th style="text-align: left"><strong>FastSpeech2</strong></th>
      <th style="text-align: left"><strong>Glow-TTS</strong></th>
      <th style="text-align: left"><strong>Tacotron 2</strong></th>
      <th style="text-align: left"><strong>VAENAR-TTS (ours)</strong></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align: left"><audio src="wavs\4.BVAE-TTS\LJ005-0100.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\5.FastSpeech2\LJ005-0100.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\3.Glow-TTS\LJ005-0100.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\2.Tacotron2\LJ005-0100.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\6.VAENAR-TTS\LJ005-0100.wav" controls="" preload=""></audio></td>
    </tr>
  </tbody>
</table>

<p>LJ006-0206. and publications which in these days would have been made the subject of a criminal prosecution.</p>

<table>
  <thead>
    <tr>
      <th style="text-align: left"><strong>BVAE-TTS</strong></th>
      <th style="text-align: left"><strong>FastSpeech2</strong></th>
      <th style="text-align: left"><strong>Glow-TTS</strong></th>
      <th style="text-align: left"><strong>Tacotron 2</strong></th>
      <th style="text-align: left"><strong>VAENAR-TTS (ours)</strong></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align: left"><audio src="wavs\4.BVAE-TTS\LJ006-0206.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\5.FastSpeech2\LJ006-0206.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\3.Glow-TTS\LJ006-0206.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\2.Tacotron2\LJ006-0206.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\6.VAENAR-TTS\LJ006-0206.wav" controls="" preload=""></audio></td>
    </tr>
  </tbody>
</table>

<p>LJ007-0177. We trust, however, that the day is at hand when this stain will be removed from the character of the city of London,</p>

<table>
  <thead>
    <tr>
      <th style="text-align: left"><strong>BVAE-TTS</strong></th>
      <th style="text-align: left"><strong>FastSpeech2</strong></th>
      <th style="text-align: left"><strong>Glow-TTS</strong></th>
      <th style="text-align: left"><strong>Tacotron 2</strong></th>
      <th style="text-align: left"><strong>VAENAR-TTS (ours)</strong></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align: left"><audio src="wavs\4.BVAE-TTS\LJ007-0177.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\5.FastSpeech2\LJ007-0177.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\3.Glow-TTS\LJ007-0177.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\2.Tacotron2\LJ007-0177.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\6.VAENAR-TTS\LJ007-0177.wav" controls="" preload=""></audio></td>
    </tr>
  </tbody>
</table>

<p>LJ013-0081. Banks and bankers continued to be victimized.</p>

<table>
  <thead>
    <tr>
      <th style="text-align: left"><strong>BVAE-TTS</strong></th>
      <th style="text-align: left"><strong>FastSpeech2</strong></th>
      <th style="text-align: left"><strong>Glow-TTS</strong></th>
      <th style="text-align: left"><strong>Tacotron 2</strong></th>
      <th style="text-align: left"><strong>VAENAR-TTS (ours)</strong></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align: left"><audio src="wavs\4.BVAE-TTS\LJ013-0081.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\5.FastSpeech2\LJ013-0081.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\3.Glow-TTS\LJ013-0081.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\2.Tacotron2\LJ013-0081.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\6.VAENAR-TTS\LJ013-0081.wav" controls="" preload=""></audio></td>
    </tr>
  </tbody>
</table>

<p>LJ038-0009. When he heard police sirens, he, quote, looked up and saw the man enter the lobby, end quote.</p>

<table>
  <thead>
    <tr>
      <th style="text-align: left"><strong>BVAE-TTS</strong></th>
      <th style="text-align: left"><strong>FastSpeech2</strong></th>
      <th style="text-align: left"><strong>Glow-TTS</strong></th>
      <th style="text-align: left"><strong>Tacotron 2</strong></th>
      <th style="text-align: left"><strong>VAENAR-TTS (ours)</strong></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align: left"><audio src="wavs\4.BVAE-TTS\LJ038-0009.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\5.FastSpeech2\LJ038-0009.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\3.Glow-TTS\LJ038-0009.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\2.Tacotron2\LJ038-0009.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\6.VAENAR-TTS\LJ038-0009.wav" controls="" preload=""></audio></td>
    </tr>
  </tbody>
</table>

<p>LJ041-0099. Powers believed that when Oswald arrived in Japan he acquired a girlfriend, quote,</p>

<table>
  <thead>
    <tr>
      <th style="text-align: left"><strong>BVAE-TTS</strong></th>
      <th style="text-align: left"><strong>FastSpeech2</strong></th>
      <th style="text-align: left"><strong>Glow-TTS</strong></th>
      <th style="text-align: left"><strong>Tacotron 2</strong></th>
      <th style="text-align: left"><strong>VAENAR-TTS (ours)</strong></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align: left"><audio src="wavs\4.BVAE-TTS\LJ041-0099.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\5.FastSpeech2\LJ041-0099.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\3.Glow-TTS\LJ041-0099.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\2.Tacotron2\LJ041-0099.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\6.VAENAR-TTS\LJ041-0099.wav" controls="" preload=""></audio></td>
    </tr>
  </tbody>
</table>

<p>LJ043-0071. His performance for that company was satisfactory.</p>

<table>
  <thead>
    <tr>
      <th style="text-align: left"><strong>BVAE-TTS</strong></th>
      <th style="text-align: left"><strong>FastSpeech2</strong></th>
      <th style="text-align: left"><strong>Glow-TTS</strong></th>
      <th style="text-align: left"><strong>Tacotron 2</strong></th>
      <th style="text-align: left"><strong>VAENAR-TTS (ours)</strong></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align: left"><audio src="wavs\4.BVAE-TTS\LJ043-0071.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\5.FastSpeech2\LJ043-0071.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\3.Glow-TTS\LJ043-0071.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\2.Tacotron2\LJ043-0071.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\6.VAENAR-TTS\LJ043-0071.wav" controls="" preload=""></audio></td>
    </tr>
  </tbody>
</table>

<p>LJ047-0234. Hosty’s initial reaction on hearing that Oswald was a suspect in the assassination, was, quote, shock</p>

<table>
  <thead>
    <tr>
      <th style="text-align: left"><strong>BVAE-TTS</strong></th>
      <th style="text-align: left"><strong>FastSpeech2</strong></th>
      <th style="text-align: left"><strong>Glow-TTS</strong></th>
      <th style="text-align: left"><strong>Tacotron 2</strong></th>
      <th style="text-align: left"><strong>VAENAR-TTS (ours)</strong></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align: left"><audio src="wavs\4.BVAE-TTS\LJ047-0234.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\5.FastSpeech2\LJ047-0234.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\3.Glow-TTS\LJ047-0234.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\2.Tacotron2\LJ047-0234.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\6.VAENAR-TTS\LJ047-0234.wav" controls="" preload=""></audio></td>
    </tr>
  </tbody>
</table>
    
  </body>
</html>

