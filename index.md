# VoiceTailor: Lightweight Plug-In Adapter for Diffusion-Based Personalized Text-to-Speech (INTERSPEECH 2024)

#### This page and the demos below are intended solely for research demonstration.

### Authors
- Heeseung Kim <a href="gmltmd789@snu.ac.kr">gmltmd789@snu.ac.kr</a>
- Sang-gil Lee <a href="sanggill@nvidia.com">sanggill@nvidia.com</a>
- Jiheum Yeom <a href="quilava1234@snu.ac.kr">quilava1234@snu.ac.kr</a>
- Che Hyun Lee <a href="saga1214@snu.ac.kr">saga1214@snu.ac.kr</a>
- Sungwon Kim <a href="sungwonk@nvidia.com">sungwonk@nvidia.com</a>
- Sungroh Yoon (Corresponding author) <a href="sryoon@snu.ac.kr">sryoon@snu.ac.kr</a>

## Abstract
We propose VoiceTailor, a parameter-efficient speaker-adaptive text-to-speech (TTS) system, by equipping a pre-trained diffusion-based TTS model with a personalized adapter. VoiceTailor identifies pivotal modules that benefit from the adapter based on a weight change ratio analysis.
We utilize Low-Rank Adaptation (LoRA) as a parameter-efficient adaptation method and incorporate the adapter into pivotal modules of the pre-trained diffusion decoder.
To achieve powerful adaptation performance with few parameters, we explore various guidance techniques for speaker adaptation and investigate the best strategies to strengthen speaker information.
VoiceTailor demonstrates comparable speaker adaptation performance to existing adaptive TTS models by fine-tuning only 0.25% of the total parameters.
VoiceTailor shows strong robustness when adapting to a wide range of real-world speakers, as shown in the demo.

## LibriTTS Dataset
**Among our baselines, YourTTS generates voices at 16kHz. Therefore, for a fair comparison, all the demos below were resampled to 16kHz and normalized to -27dB.**

### Model Comparison

Transcript: The second passed in height The first, and sought the forehead, and half missed, Half falling on the hair.

<table>
	<thead>
		<tr>
			<th style="text-align: center">Reference</th>
			<th style="text-align: center">GT</th>
			<th style="text-align: center">Vocoder (BigVGAN)</th>
			<th style="text-align: center">VoiceTailor</th>
			<th style="text-align: center">UnitSpeech</th>
			<th style="text-align: center">XTTS $v2$</th>
			<th style="text-align: center">YourTTS</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_16k_TTS/1_reference.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_16k_TTS/1_gt.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_16k_TTS/1_bigvgan.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_16k_TTS/1_voicetailor.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_16k_TTS/1_unitspeech.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_16k_TTS/1_xtts.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_16k_TTS/1_yourtts.wav" type="audio/wav"></audio></td>
		</tr>
	</tbody>
</table>

Transcript: But from the offer that came to teach Negroes-country Negroes, and little ones at that-she shrank, and, indeed, probably would have refused it out of hand had it not been for her queer brother, john.

<table>
	<thead>
		<tr>
			<th style="text-align: center">Reference</th>
			<th style="text-align: center">GT</th>
			<th style="text-align: center">Vocoder (BigVGAN)</th>
			<th style="text-align: center">VoiceTailor</th>
			<th style="text-align: center">UnitSpeech</th>
			<th style="text-align: center">XTTS $v2$</th>
			<th style="text-align: center">YourTTS</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_16k_TTS/2_reference.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_16k_TTS/2_gt.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_16k_TTS/2_bigvgan.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_16k_TTS/2_voicetailor.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_16k_TTS/2_unitspeech.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_16k_TTS/2_xtts.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_16k_TTS/2_yourtts.wav" type="audio/wav"></audio></td>
		</tr>
	</tbody>
</table>

Transcript: So, with a great many chucklings and shruggings when no one was by, he had departed after breakfast one day, simply saying he shouldn't be back to lunch.

<table>
	<thead>
		<tr>
			<th style="text-align: center">Reference</th>
			<th style="text-align: center">GT</th>
			<th style="text-align: center">Vocoder (BigVGAN)</th>
			<th style="text-align: center">VoiceTailor</th>
			<th style="text-align: center">UnitSpeech</th>
			<th style="text-align: center">XTTS $v2$</th>
			<th style="text-align: center">YourTTS</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_16k_TTS/3_reference.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_16k_TTS/3_gt.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_16k_TTS/3_bigvgan.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_16k_TTS/3_voicetailor.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_16k_TTS/3_unitspeech.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_16k_TTS/3_xtts.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_16k_TTS/3_yourtts.wav" type="audio/wav"></audio></td>
		</tr>
	</tbody>
</table>

### Ablation Studies

#### Lora Rank $r$

Transcript: Then they started on again and two hours later came in sight of the house of dr Pipt.

<table>
	<thead>
		<tr>
			<th style="text-align: center">Reference</th>
			<th style="text-align: center">$r=2$</th>
			<th style="text-align: center">$r=4$</th>
			<th style="text-align: center">$r=8$</th>
			<th style="text-align: center">$r=16$ <strong>(default)</strong></th>
			<th style="text-align: center">$r=32$</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_rank_ablation/1_reference.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_rank_ablation/1_r2.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_rank_ablation/1_r4.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_rank_ablation/1_r8.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_rank_ablation/1_r16.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_rank_ablation/1_r32.wav" type="audio/wav"></audio></td>
		</tr>
	</tbody>
</table>

Transcript: But when the pick was shipped again, Hans pointed out on its surface deep prints as if it had been violently compressed between two hard bodies.


<table>
	<thead>
		<tr>
			<th style="text-align: center">Reference</th>
			<th style="text-align: center">$r=2$</th>
			<th style="text-align: center">$r=4$</th>
			<th style="text-align: center">$r=8$</th>
			<th style="text-align: center">$r=16$ <strong>(default)</strong></th>
			<th style="text-align: center">$r=32$</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_rank_ablation/2_reference.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_rank_ablation/2_r2.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_rank_ablation/2_r4.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_rank_ablation/2_r8.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_rank_ablation/2_r16.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_rank_ablation/2_r32.wav" type="audio/wav"></audio></td>
		</tr>
	</tbody>
</table>

Transcript: Also, a draft on futurity, sometimes honored, but generally extended.

<table>
	<thead>
		<tr>
			<th style="text-align: center">Reference</th>
			<th style="text-align: center">$r=2$</th>
			<th style="text-align: center">$r=4$</th>
			<th style="text-align: center">$r=8$</th>
			<th style="text-align: center">$r=16$ <strong>(default)</strong></th>
			<th style="text-align: center">$r=32$</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_rank_ablation/3_reference.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_rank_ablation/3_r2.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_rank_ablation/3_r4.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_rank_ablation/3_r8.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_rank_ablation/3_r16.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_rank_ablation/3_r32.wav" type="audio/wav"></audio></td>
		</tr>
	</tbody>
</table>

#### Speaker Condition Strengthen Methods

- w/o strengthening: No additional methods applied
- LoRA scale adjustment: Using a larger $\alpha$ value for inference than the $\alpha$ value used during fine-tuning.
- Speaker embedding guidance: When calculating the unconditional score, LoRA is plugged in as is, only replacing speaker embedding $e_S$ with unconditional embedding $e_\phi$.
- LoRA guidance: When calculating the unconditional score, embedding $e_S$ is provided as is, only plugging out the low-rank adaptor.
- Embedding & LoRA guidance: Removing all speaker information when calculating the unconditional score.

Transcript: And therefore, primarily, they must be able to divide so that elementary exercises in color must be directed, like first exercises in music, to the clear separation of notes and the final perfections of color are those in which, of innumerable notes or hues, every one has a distinct office, and can be fastened on by the eye, and approved, as fulfilling it.

<table>
	<thead>
		<tr>
			<th style="text-align: center">Reference</th>
			<th style="text-align: center">w/o strengthening</th>
			<th style="text-align: center">LoRA scale adjustment $(2 \cdot \alpha)$</th>
			<th style="text-align: center"><strong>Speaker embedding guidance with</strong> $\gamma_S=1$ <strong>(default)</strong></th>
			<th style="text-align: center">Speaker embedding guidance with $\gamma_S=2$</th>
			<th style="text-align: center">LoRA guidance with $\gamma_S=1$</th>
			<th style="text-align: center">LoRA guidance with $\gamma_S=2$</th>
			<th style="text-align: center">Embedding & LoRA guidance with $\gamma_S=1$</th>
			<th style="text-align: center">Embedding & LoRA guidance with $\gamma_S=2$</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_strengthen_ablation/1_reference.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_strengthen_ablation/1_wos.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_strengthen_ablation/1_loras.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_strengthen_ablation/1_seg1.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_strengthen_ablation/1_seg2.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_strengthen_ablation/1_lg1.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_strengthen_ablation/1_lg2.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_strengthen_ablation/1_elg1.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_strengthen_ablation/1_elg2.wav" type="audio/wav"></audio></td>
		</tr>
	</tbody>
</table>

Transcript: He shrugged his shoulders in ungracious acquiescence, while our visitor in hurried words and with much excitable gesticulation poured forth his story.

<table>
	<thead>
		<tr>
			<th style="text-align: center">Reference</th>
			<th style="text-align: center">w/o strengthening</th>
			<th style="text-align: center">LoRA scale adjustment $(2 \cdot \alpha)$</th>
			<th style="text-align: center"><strong>Speaker embedding guidance with</strong> $\gamma_S=1$ <strong>(default)</strong></th>
			<th style="text-align: center">Speaker embedding guidance with $\gamma_S=2$</th>
			<th style="text-align: center">LoRA guidance with $\gamma_S=1$</th>
			<th style="text-align: center">LoRA guidance with $\gamma_S=2$</th>
			<th style="text-align: center">Embedding & LoRA guidance with $\gamma_S=1$</th>
			<th style="text-align: center">Embedding & LoRA guidance with $\gamma_S=2$</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_strengthen_ablation/2_reference.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_strengthen_ablation/2_wos.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_strengthen_ablation/2_loras.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_strengthen_ablation/2_seg1.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_strengthen_ablation/2_seg2.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_strengthen_ablation/2_lg1.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_strengthen_ablation/2_lg2.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_strengthen_ablation/2_elg1.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_strengthen_ablation/2_elg2.wav" type="audio/wav"></audio></td>
		</tr>
	</tbody>
</table>

Transcript: If a man had stolen a pound in his youth and had used that pound to amass a huge fortune how much was he obliged to give back, the pound he had stolen only or the pound together with the compound interest accruing upon it or all his huge fortune?

<table>
	<thead>
		<tr>
			<th style="text-align: center">Reference</th>
			<th style="text-align: center">w/o strengthening</th>
			<th style="text-align: center">LoRA scale adjustment $(2 \cdot \alpha)$</th>
			<th style="text-align: center"><strong>Speaker embedding guidance with</strong> $\gamma_S=1$ <strong>(default)</strong></th>
			<th style="text-align: center">Speaker embedding guidance with $\gamma_S=2$</th>
			<th style="text-align: center">LoRA guidance with $\gamma_S=1$</th>
			<th style="text-align: center">LoRA guidance with $\gamma_S=2$</th>
			<th style="text-align: center">Embedding & LoRA guidance with $\gamma_S=1$</th>
			<th style="text-align: center">Embedding & LoRA guidance with $\gamma_S=2$</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_strengthen_ablation/3_reference.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_strengthen_ablation/3_wos.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_strengthen_ablation/3_loras.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_strengthen_ablation/3_seg1.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_strengthen_ablation/3_seg2.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_strengthen_ablation/3_lg1.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_strengthen_ablation/3_lg2.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_strengthen_ablation/3_elg1.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Libri_strengthen_ablation/3_elg2.wav" type="audio/wav"></audio></td>
		</tr>
	</tbody>
</table>

## Real-world Scenarios
To avoid copyright and misuse issues, we have removed the real-world scenarios.
