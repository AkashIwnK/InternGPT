[[中文文档]](README_CN.md)

**The project is still under construction, we will continue to update it and welcome contributions/pull requests from the community.**

<p align="center"><img src="./assets/gvlab_logo.png" width="600"></p>

<a src="https://img.shields.io/discord/1099920215724277770?label=Discord&logo=discord" href="https://discord.gg/khWBFnCgAN">
    <img src="https://img.shields.io/discord/1099920215724277770?label=Discord&logo=discord"> </a> | <a src="https://img.shields.io/badge/GPU%20Demo-Open-green?logo=alibabacloud" href="https://ichat.opengvlab.com">
    <img src="https://img.shields.io/badge/Demo-Open-green?logo=alibabacloud"> </a> | <a src="https://img.shields.io/twitter/follow/opengvlab?style=social" href="https://twitter.com/opengvlab">
    <img src="https://img.shields.io/twitter/follow/opengvlab?style=social">  </a> 
    


# InternGPT [[paper](https://arxiv.org/pdf/2305.05662.pdf)][[play it](https://igpt.opengvlab.com/)]


<!-- ## Description -->
**InternGPT**(short for **iGPT**) is pointing-language-driven visual interactive system, allowing you to interact with ChatGPT by clicking, dragging and drawing using a pointing device. The name InternGPT stands for **inter**action, **n**onverbal, and Chat**GPT**. Different from existing interactive systems that rely on pure language, by incorporating pointing instructions, iGPT significantly improves the efficiency of communication between users and chatbots, as well as the accuracy of chatbots in vision-centric tasks, especially in complicated visual scenarios. Additionally, in iGPT, an auxiliary control mechanism is used to improve the control capability of LLM, and a large vision-language model termed **Husky** is fine-tuned for high-quality multi-modal dialogue (impressing ChatGPT-3.5-turbo with **93.89% GPT-4 Quality**).

## Online Demo
[**NOTE**] It is possible that you are waiting in a lengthy queue. You can clone our repo and run it with your private GPU.

[**InternGPT**](https://igpt.opengvlab.com/) is online. Let's try it!


https://github.com/OpenGVLab/InternGPT/assets/8529570/a02bcea5-6d1f-4e84-85a3-8a66239b8a51





## Schedule
- [ ] Support Chinese
- [ ] Support MOSS
- [ ] More powerful foundation models based on [InternImage](https://github.com/OpenGVLab/InternImage) and [InternVideo](https://github.com/OpenGVLab/InternVideo)
- [ ] More accurate interactive experience
- [ ] OpenMMLab Toolkit
- [ ] Web page & code generation 
- [x] Support voice assistant
- [x] Support click interaction
- [x] Interactive image editing
- [x] Interactive image generation
- [x] Interactive visual question answering
- [x] Segment Anything
- [x] Image inpainting
- [x] Image caption
- [x] image matting
- [x] Optical character recognition
- [x] Action recognition
- [x] Video caption
- [x] Video dense caption
- [x] video highlight interpretation



## System Overview
<p align="center"><img src="./assets/arch1.png" alt="Logo"></p>

## 🎁 Major Features
<!--<!-- <p align="center"><img src="./assets/online_demo.gif" alt="Logo"></p> -->  
<p align="center">(a) Remove the masked object</p>
<p align="center"><img src="./assets/demo2.gif" width="500"></p>

<p align="center">(b) Interactive image editing</center>
<p align="center"><img src="./assets/tower.gif" width="500"></p>

<p align="center">(c) Image generation</p>
<p align="center"><img src="./assets/demo4.gif" align='justify'  width="500"></p>

<p align="center">(d) Interactive visual question answer</p>
<p align="center"><img src="./assets/demo5.gif" align='justify' width="700"></p> 


<p align="center">(e) Interactive image generation</p>
<p align="center"><img width="800" alt="image" src="https://github.com/OpenGVLab/InternGPT/assets/8529570/2b0da08e-af86-453d-99e5-1327f93aa917"></p> 


<p align="center">(f) Video highlight interpretation</p>
<p align="center"><img src="./assets/demo6.jpg" align='justify' width="500"></p> 

<!-- ![alt]("./assets/demo5.gif" "title") -->


## 🛠️ Installation

### Basic requirements

- Linux
- Python 3.8+
- PyTorch 1.12+
- CUDA 11.6+ 
- GCC & G++ 5.4+
- GPU Memory >= 17G for loading basic tools (HuskyVQA, SegmentAnything, ImageOCRRecognition)

### Install Python dependencies
```shell
pip install -r requirements.txt
```

### Model zoo
Coming soon...

## 👨‍🏫 Get Started 
Running the following shell can start a gradio service:
```shell
python -u app.py --load "HuskyVQA_cuda:0,SegmentAnything_cuda:0,ImageOCRRecognition_cuda:0" --port 3456
```

if you want to enable the voice assistant, please use `openssl` to generate the certificate:
```shell
mkdir certificate
openssl req -x509 -newkey rsa:4096 -keyout certificate/key.pem -out certificate/cert.pem -sha256 -days 365 -nodes
```

and then run:
```shell
python -u app.py --load "HuskyVQA_cuda:0,SegmentAnything_cuda:0,ImageOCRRecognition_cuda:0" --port 3456 --https
```


## 🎫 License

This project is released under the [Apache 2.0 license](LICENSE). 

## 🖊️ Citation

If you find this project useful in your research, please consider cite:
```BibTeX
@misc{2023interngpt,
    title={InternGPT: Solving Vision-Centric Tasks by Interacting with ChatGPT Beyond Language},
    author={Zhaoyang Liu and Yinan He and Wenhai Wang and Weiyun Wang and Yi Wang and Shoufa Chen and Qinglong Zhang and Yang Yang and Qingyun Li and Jiashuo Yu and Kunchang Li and Zhe Chen and Xue Yang and Xizhou Zhu and Yali Wang and Limin Wang and Ping Luo and Jifeng Dai and Yu Qiao},
    howpublished = {\url{https://arxiv.org/abs/2305.05662}},
    year={2023}
}
```

## 🤝 Acknowledgement
Thanks to the open source of the following projects:

[Hugging Face](https://github.com/huggingface) &#8194;
[LangChain](https://github.com/hwchase17/langchain) &#8194;
[TaskMatrix](https://github.com/microsoft/TaskMatrix) &#8194;
[SAM](https://github.com/facebookresearch/segment-anything) &#8194;
[Stable Diffusion](https://github.com/CompVis/stable-diffusion) &#8194; 
[ControlNet](https://github.com/lllyasviel/ControlNet) &#8194; 
[InstructPix2Pix](https://github.com/timothybrooks/instruct-pix2pix) &#8194; 
[BLIP](https://github.com/salesforce/BLIP) &#8194;
[Latent Diffusion Models](https://github.com/CompVis/latent-diffusion) &#8194;
[EasyOCR](https://github.com/JaidedAI/EasyOCR) &#8194;

Welcome to discuss with us and continuously improve the user experience of InternGPT.

WeChat QR Code

<p align="center"><img width="500" alt="image" src="https://s1.ax1x.com/2023/05/11/p9r7JSA.jpg"></p> 

