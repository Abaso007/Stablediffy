<div align="center">
  <img src="https://user-images.githubusercontent.com/83492589/231606495-83f38148-e78f-4ea4-a35b-dd2fc8863d82.png" width="500" height="300" />
  
  
  
  # Stablediffy 

  *A vicuna based prompt engineering tool for stable diffusion*
  
  **generate awesome images without prompt knowledge**
  
  
  
  <a href="#examples">Examples</a> - <a href="#installation">Installation</a> - <a href="#usage">Usage</a>

  
</div>

## How it works
The Stablediffy.txt file is a prompt-file for the vicuna model, similar to the chat-with-bob.txt file.<br>
First, The situation is described.
Secondly, a few keywords like "dramatic lightning" are listed, to teach vicuna them.
Third, a few sample responses from Stablediffy to the rough sentences from the Human are listed, to teach vicuna how it should respond.


## Examples
### 1. Suggest a prompt for an mysterious house
<img src="https://user-images.githubusercontent.com/83492589/231573450-efc41738-9d7b-47d2-baee-8483984a25a7.png" width="600" height="600" /> 
Model: Deliberate - 768x768 - Sampling Method: Euler a - Sampling Steps: 20

#### Request
```
### Human:suggest a prompt for an mysterious house
### Assistant: Mysterious house, haunted mansion, spooky, intricate, sharp details, octane render, unreal engine, photograph, realistic skin texture, photorealistic, hyper realism, highly detailed, 85mm portrait photography, award winning, hard rim lighting photography, dramatic lighting, cinematic lighting, gritty atmosphere, urban, noir style, night scene"
```
### 2. Suggest a prompt for a mysterious lake in the night

<img src="https://user-images.githubusercontent.com/83492589/231817378-63775127-1f46-4a3b-b1dc-18171542c621.png" width="600" height="600" /> 
Model: Deliberate - 768x768 - Sampling Method: Euler a - Steps: 20 - Seed: 2063493670

#### Request
```
### Human:suggest a prompt for a mysterious lake in the night
### Assistant: Mysterious lake, night scene, dark and moody, atmospheric, spooky, gothic, creepy, haunting, eerie, suspenseful, dramatic lightning, cinematic lightning, octane render, unreal engine, realistic reflections, water reflections, moonlight, starry sky, mysterious atmosphere, dark and gritty
```
### 3. Suggest a prompt for a ghost ship on the ocean

<img src="https://user-images.githubusercontent.com/83492589/231880244-4e3e8555-e0b0-4096-9070-195e632dd402.png" width="600" height="600" /> 
Model: Deliberate - 768x768 - Sampling Method: Euler a - Steps: 20 - Seed: 304886124

#### Request
```
### Human:suggest a prompt for a ghost ship on the ocean
### Assistant: Ghost ship, abandoned ship, creepy atmosphere, spooky, dark, ominous, mysterious, cinematic lightning, dramatic lightning, octane render, unreal engine, realistic, highly detailed, textured, 3D modeling, digital art, 3D illustration
```

### 4. Suggest a prompt for a portrait of Danial Craig
<img src="https://user-images.githubusercontent.com/83492589/231801089-9ac5238a-0282-4997-a2f6-e4c405df1fe6.png" width="600" height="600" /> 
Model: Deliberate - 768x768 - Sampling Method: Euler a - Steps: 20 - Seed: 874348722

#### Request
```
### Human:suggest a prompt for a portrait of Danial Craig
### Assistant: Daniel Craig portrait, actor, famous, well-known, blue eyes, chiseled jawline, suave, sophisticated, realistic, hyper-realistic, highly detailed, 85mm lens, photography, realistic skin texture, photorealistic, noir style, cinematic lightning, dramatic lightning, portrait photography, sharp focus, colorful"
```


## Installation
To install Vicuna, follow the instructions on this repo: https://github.com/vicuna-tools/vicuna-installation-guide/

Once that's done, navigate to the `llama.cpp/prompts` folder

Now, download the Stablediffy.txt file with `wget`
```
wget "https://raw.githubusercontent.com/vicuna-tools/Stablediffy.txt/main/Stablediffy.txt"
```
## Usage 
Navigate back to the `llama.cpp` folder
Run the vicuna model with the Stablediffy.txt prompt-file
```
./main -m ./models/vicuna-13B-1.1-GPTQ-4bit-128g.GGML.bin --repeat_penalty 1.0 --color -i -r "### Human:" -f prompts/Stablediffy.txt
```
This should start processing the Stablediffy.txt file
After the last processed conversation example:

`### Assistant: Car in 1950, highly detailed, classic car, 1950's...`

#### You should see the prompt-input `### Human:`, there you can start asking for stable diffusion prompts

![untitled](https://user-images.githubusercontent.com/83492589/231721945-e58890ed-ac13-4872-a2ae-d1d918b2ca00.gif)
