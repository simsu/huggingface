# huggingface
huggingface document translation project

[\[원본링크\]](https://huggingface.co/docs/diffusers/v0.14.0/en/api/pipelines/stable_diffusion/text2img)

## Text-to-Image Generation

### StableDiffusionPipeline

스테이블 확산 모델은 CompVis와 Stability AI, runway 그리고 LAION에 의해 만들어졌다. 스테이블 확산 파이프라인은 스테이블 디퓨젼을 사용하여 텍스트 입력이 주어지면 사실적인 사진 이미지를 생성할 수 있습니다.

기존의 코드베이스는 이곳에서 찾을 수 있습니다:

 - Stable Diffusion V1: CompVis/stable-diffusion
 - Stable Diffusion v2: Stability-AI/stablediffusion
 
 가능한 체크포인트들은 이곳에서 찾을 수 있습니다:
 
 - stable-diffusion-v1-4 (512x512 resolution) CompVis/stable-diffusion-v1-4
 - stable-diffusion-v1-5 (512x512 resolution) runwayml/stable-diffusion-v1-5
 - stable-diffusion-2-base (512x512 resolution): stabilityai/stable-diffusion-2-base
 - stable-diffusion-2 (768x768 resolution): stabilityai/stable-diffusion-2
 - stable-diffusion-2-1-base (512x512 resolution) stabilityai/stable-diffusion-2-1-base
 - stable-diffusion-2-1 (768x768 resolution): stabilityai/stable-diffusion-2-1
 
```
class diffusers.StableDiffusionPipeline
 ( vae: AutoencoderKLtext_encoder: CLIPTextModeltokenizer: CLIPTokenizerunet: UNet2DConditionModelscheduler: KarrasDiffusionSchedulerssafety_checker: StableDiffusionSafetyCheckerfeature_extractor: CLIPFeatureExtractorrequires_safety_checker: bool = True )
```
> Parameters
 > - vae (AutoencoderKL) — 잠재 표현에 대한 이미지를 인코딩하고 디코드하는 VAE(Variational Auto-Encoder) 모델 
 > - text_encoder (CLIPTextModel) — 얼은 텍스트 인코더. 스테이블 디퓨젼은 CLIP의 텍스트 부분, 특히 clip-vit-large-patch14 variant를 사용합니다. 
 > - tokenizer (CLIPTokenizer) — CLIPTokenizer 클래스의 Tokenizer.
 > - unet (UNet2DConditionModel) — 인코딩된 이미지의 레이턴스를 없애기 위해 사용하는 조건부 U-Net아키텍쳐.
 > - scheduler (SchedulerMixin) — 인코딩된 이미지 레이턴스를 없애기 위해 unet 결합에 사용될 스케줄러. DDIM스케줄러, LMSDiscrete스케줄러, PNDM스케줄러 중 하나
 > - safety_checker (StableDiffusionSafetyChecker) — 만들어진 이미지들이 불쾌감을 주거나 해로운지 아닌지 평가하는 단일화 모듈.  자세한 내용은 모델 카드를 참조하십시오
 > - feature_extractor (CLIPFeatureExtractor) — safety_checker를 위한 인풋으로 사용될지 만들어진 이미지에서 특징들을 추출하는 모델 <br/><br/>
 > 스테이블 디퓨전을 사용한 text-to-image 생성을 위한 파이프라인 <br/><br/>
 > 이 모델은 DiffusionPipeline으로부터 상속받습니다. 라이브러리가 모든 파이프라인에 대해 구현되는 일반적인 방법은 수퍼클레스 문서를 참조하십시오. (다운로드나 저장, 부분적인 장치에서의 실행 등..)
