# TorchRWKV

TorchRWKV is a pure PyTorch implementation of the RWKV large language model inference framework. This project aims to provide a flexible and easily scalable PyTorch implementation for the RWKV x060 model, supporting various features such as batch inference, parallel inference, ONNX format export, and standalone training.

## Features

- Native PyTorch implementation
- Batch inference support
- Parallel inference to fully leverage RWKV advantages
- Clean, readable, and easily extendable codebase
- ONNX format model export and inference
- Simple standalone training

## Hardware Support

We support various hardware devices, including but not limited to:
- NVIDIA GPUs
- Intel GPUs
- AMD GPUs
- Moore Thread MUSA GPUs
- Huawei Ascend NPUs

Contributions for additional device support are welcome.

## Installation and Usage

1. Clone the repository:
   ```
   git clone -b dev https://github.com/uniartisan/TorchRWKV.git
   ```

2. Install dependencies:
   ```
   cd TorchRWKV
   pip install -r requirements.txt
   ```

3. Download the RWKV6 model from [BlinkDL/rwkv-6-world](https://huggingface.co/BlinkDL/rwkv-6-world/tree/main) and place the weights in the `weight` folder.

4. Modify the `MODEL_NAME` parameter in `main.py`.

5. Run the inference:
   ```
   python main.py
   ```

## ONNX Export

1. Modify parameters in `onnx_export.py` for your desired model.
2. Run:
   ```
   python onnx_export.py
   ```
3. (Optional) Create a directory for simplified models:
   ```
   mkdir ONNX_Simplified
   ```
4. (Optional) Simplify the model:
   ```
   python simplify_large_onnx.py -m onnx/{model name}.onnx -o ONNX_Simplified/{model name}.onnx
   ```
5. (Optional) Modify the model path in `onnx_infer.py` and run:
   ```
   python onnx_infer.py
   ```

## Local Deployment

1. Modify model configuration in `openai_api.py`.
2. Start the backend:
   ```
   python openai_api.py
   ```
3. Use any OpenAI API-compatible client with `http://127.0.0.1:8848` as the `API_URL`.

## Note

This framework currently supports only RWKV v6 models, specifically version x060.

## Future Plans

We plan to adapt this project for the AI Pro development board launched by Xunlong Orange Pi, enabling inference of the RWKV model on the Ascend ecosystem.


## Acknowledgements

Special thanks to:
- Yang, S., & Zhang, Y. (2024). FLA: A Triton-Based Library for Hardware-Efficient Implementations of Linear Attention Mechanism (Version 0.0.1) [Computer software]. https://github.com/sustcsonglin/flash-linear-attention

- [onnxsim_large_model](https://github.com/luchangli03/onnxsim_large_model.git)

We have used modified implementations based on their work in different kernels.

## Contributing

We welcome contributions from the community. Please feel free to submit PRs and raise Issues. Your input is valuable and helps improve the project for everyone.

****

优化模型用到的仓库：

## 贡献者 (Contributors)

<!-- readme: collaborators,contributors -start -->
<table>
	<tbody>
		<tr>
            <td align="center">
                <a href="https://github.com/uniartisan">
                    <img src="https://avatars.githubusercontent.com/u/31544054?v=4" width="100;" alt="uniartisan"/>
                    <br />
                    <sub><b>Zhiyuan Li</b></sub>
                </a>
            </td>
            <td align="center">
                <a href="https://github.com/yuunnn-w">
                    <img src="https://avatars.githubusercontent.com/u/91336323?v=4" width="100;" alt="yuunnn-w"/>
                    <br />
                    <sub><b>Yuunnn_w</b></sub>
                </a>
            </td>
            <td align="center">
                <a href="https://github.com/WuTianyi321">
                    <img src="https://avatars.githubusercontent.com/u/48122470?v=4" width="100;" alt="WuTianyi321"/>
                    <br />
                    <sub><b>WuTianyi</b></sub>
                </a>
            </td>
            <td align="center">
                <a href="https://github.com/jiamingkong">
                    <img src="https://avatars.githubusercontent.com/u/2761215?v=4" width="100;" alt="jiamingkong"/>
                    <br />
                    <sub><b>Null</b></sub>
                </a>
            </td>
            <td align="center">
                <a href="https://github.com/Aknifejackzhmolong">
                    <img src="https://avatars.githubusercontent.com/u/23431216?v=4" width="100;" alt="Aknifejackzhmolong"/>
                    <br />
                    <sub><b>Dejiao Zeng</b></sub>
                </a>
            </td>
		</tr>
	<tbody>
</table>
<!-- readme: collaborators,contributors -end -->

****
## Technical Exchange Group

![QQ交流群](https://github.com/yuunnn-w/TorchRWKV/blob/main/asset/qrcode_1713112204738.jpg)

****


**We warmly invite everyone to contribute to the project by submitting PRs and raising Issues! Your input and contributions are highly valued and play a vital role in improving the project for the entire community. Let's collaborate and make this project even better together!**


