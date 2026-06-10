# Explainability Methods in Computer Vision

This repository provides a structured and curated collection of papers on explainability methods for vision models, covering both classical and recent approaches.

## Taxonomy Overview
We follow prior surveys while extending coverage to:
- Transformer-based architectures (e.g., ViTs)
- Multimodal vision-language models
- Intrinsically interpretable models

### Types of Explanations
- Saliency maps
- Concept-based explanations
- Prototype-based explanations
- Counterfactual explanations
- Decision tree-based explanations
- Textual rationales
- Clustering-based explanations

### Explanation Dimensions
- A/P: Ante-hoc vs. Post-hoc
- A/S: Model-agnostic vs. Model-specific
- G/L: Global vs. Local explanations

> **Ante-hoc** methods are interpretable by design, whereas **post-hoc** methods provide
explanations only after a model has been trained. For post-hoc approaches,
we additionally distinguish between **model-agnostic** methods, which can be
applied to any query-only black-box model, and **model-specific** methods, which
require access to internal information such as gradients or activations, or
rely on particular architectural assumptions. We also classify explanations
according to their scope: **global** methods aim to characterize the overall
behavior of a model, whereas **local** methods explain individual predictions.
These attributes are not reported for ante-hoc methods, since when
interpretability is embedded directly into the model, both the applicability
of the explanation mechanism and its scope are less naturally defined.

| Method | Year | Type of explanation | A/P | A/S | G/L | Code | Ref. |
|---|---:|---|:---:|:---:|:---:|:---:|:---:|
| LIME | 2016 | Saliency map | P | A | L | [link](https://github.com/marcotcr/lime) | [1](#ref-1) |
| SHAP | 2017 | Saliency map | P | A | L | [link](https://github.com/shap/shap) | [2](#ref-2) |
| Meaningful Perturbation | 2017 | Saliency map | P | A | L | [link](https://github.com/ruthcfong/perturb_explanations?utm_source=chatgpt.com) | [3](#ref-3) |
| RISE | 2018 | Saliency map | P | A | L | [link](https://github.com/eclique/RISE) | [4](#ref-4) |
| L2X | 2018 | Saliency map | P | A | L | [link](https://github.com/Jianbo-Lab/L2X) | [5](#ref-5) |
| LRP | 2016 | Saliency map | P | S | L | [link](https://github.com/sebastian-lapuschkin/lrp_toolbox) | [6](#ref-6) |
| SmoothGrad | 2017 | Saliency map | P | S | L | [link](https://github.com/PAIR-code/saliency) | [7](#ref-7) |
| Integrated Gradients | 2017 | Saliency map | P | S | L | [link](https://github.com/ankurtaly/Integrated-Gradients) | [8](#ref-8) |
| DeepLift | 2017 | Saliency map | P | S | L | [link](https://github.com/kundajelab/deeplift) | [9](#ref-9) |
| Grad-CAM | 2017 | Saliency map | P | S | L | [link](https://github.com/ramprs/grad-cam/) | [10](#ref-10) |
| Grad-CAM++ | 2018 | Saliency map | P | S | L | [link](https://github.com/adityac94/Grad_CAM_plus_plus) | [11](#ref-11) |
| XRAI | 2019 | Saliency map | P | S | L | [link](https://github.com/PAIR-code/saliency) | [12](#ref-12) |
| Attention Rollout | 2020 | Saliency map | P | S | L | [link](https://github.com/samiraabnar/attention_flow) | [13](#ref-13) |
| Transformer Attribution | 2021 | Saliency map | P | S | L | [link](https://github.com/hila-chefer/Transformer-Explainability) | [14](#ref-14) |
| TCAV | 2018 | Concept attribution | P | S | G | [link](https://github.com/tensorflow/tcav) | [15](#ref-15) |
| ACE | 2019 | Concept attribution | P | S | G | [link](https://github.com/amiratag/ACE) | [16](#ref-16) |
| FACE | 2025 | Concept attribution | P | S | G | [link](https://github.com/dipkamal/FACE) | [17](#ref-17) |
| Interpretable CNNs | 2018 | Concept attribution | P | S | G | [link](https://github.com/zqs1022/interpretableCNN) | [18](#ref-18) |
| SENN | 2018 | Concept attribution | A |  |  | [link](https://github.com/dmelis/SENN) | [19](#ref-19) |
| Interpreting CNNs via DT | 2019 | Concept attribution / Decision Tree | P | A | G | - | [20](#ref-20) |
| CACE | 2019 | Concept attribution / Counterfactuals | A |  |  | - | [21](#ref-21) |
| Concept SHAP | 2020 | Concept attribution | P | S | G | - | [22](#ref-22) |
| Concept Whitening | 2020 | Concept attribution | A |  |  | [link](https://github.com/zhiCHEN96/ConceptWhitening) | [23](#ref-23) |
| CBM | 2020 | Concept attribution | A |  |  | [link](https://github.com/yewsiang/ConceptBottleneck) | [24](#ref-24) |
| CEM | 2022 | Concept attribution | A |  |  | [link](https://github.com/mateoespinosa/cem/) | [25](#ref-25) |
| MMD-critic | 2016 | Prototypes | A |  |  | [link](https://github.com/BeenKim/MMD-critic) | [26](#ref-26) |
| Influence Functions | 2017 | Prototypes | P | S | L | [link](https://github.com/kohpangwei/influence-release) | [27](#ref-27) |
| Representer Points | 2018 | Prototypes | P | S | L | [link](https://github.com/chihkuanyeh/Representer_Point_Selection) | [28](#ref-28) |
| TracIn | 2020 | Prototypes | P | S | L | [link](https://github.com/frederick0329/TracIn) | [29](#ref-29) |
| ProtoPNet | 2019 | Prototypes | A |  |  | [link](https://github.com/cfchen-duke/ProtoPNet) | [30](#ref-30) |
| ProtoTree | 2021 | Prototypes / Decision Tree | A |  |  | [link](https://github.com/M-Nauta/ProtoTree) | [31](#ref-31) |
| ProtoPairNet | 2025 | Prototypes | A |  |  | [link](https://github.com/Rose32/ProtoPairNet) | [32](#ref-32) |
| ViT-NeT | 2022 | Prototypes / Decision Tree | A |  |  | [link](https://github.com/jumpsnack/ViT-NeT) | [33](#ref-33) |
| Contrastive Explanations | 2018 | Counterfactuals | P | S | L | [link](https://github.com/IBM/Contrastive-Explanation-Method) | [34](#ref-34) |
| CVE | 2019 | Counterfactuals | P | A | L | - | [35](#ref-35) |
| ABELE | 2020 | Counterfactuals | P | A | L | [link](https://github.com/riccotti/ABELE) | [36](#ref-36) |
| Guided Prototypes | 2021 | Counterfactuals | P | A | L | [link](https://github.com/SeldonIO/alibi) | [37](#ref-37) |
| GANterfactual | 2022 | Counterfactuals | P | A | L | [link](https://github.com/hcmlab/GANterfactual) | [38](#ref-38) |
| DiME | 2022 | Counterfactuals | P | S | L | [link](https://github.com/guillaumejs2403/DiME) | [39](#ref-39) |
| PJ-X | 2018 | Textual rationale / Saliency map | A |  |  | [link](https://github.com/Seth-Park/MultimodalExplanations) | [40](#ref-40) |
| Faithful Explanation for VQA | 2019 | Textual rationale / Image Segmentation | A |  |  | - | [41](#ref-41) |
| DDCoT | 2023 | Textual rationale (CoT) | A |  |  | [link](https://github.com/SooLab/DDCOT) | [42](#ref-42) |
| CoC | 2023 | Cluster assignments | A |  |  | [link](https://github.com/ma-xu/Context-Cluster) | [43](#ref-43) |
| FEC | 2024 | Cluster assignments | A |  |  | [link](https://github.com/guikunchen/FEC/) | [44](#ref-44) |

## References


<a id="ref-1"></a>[1] Marco Tulio Ribeiro, Sameer Singh, and Carlos Guestrin. “Why should I trust you?” Explaining the predictions of any classifier. In *Proceedings of the 22nd ACM SIGKDD International Conference on Knowledge Discovery and Data Mining*, pages 1135–1144, 2016.

<a id="ref-2"></a>[2] Scott M. Lundberg and Su-In Lee. A unified approach to interpreting model predictions. *Advances in Neural Information Processing Systems*, 30, 2017.

<a id="ref-3"></a>[3] Ruth C. Fong and Andrea Vedaldi. Interpretable explanations of black boxes by meaningful perturbation. In *Proceedings of the IEEE International Conference on Computer Vision*, pages 3429–3437, 2017.

<a id="ref-4"></a>[4] Vitali Petsiuk, Abir Das, and Kate Saenko. RISE: Randomized input sampling for explanation of black-box models. *arXiv preprint arXiv:1806.07421*, 2018.

<a id="ref-5"></a>[5] Jianbo Chen, Le Song, Martin Wainwright, and Michael Jordan. Learning to explain: An information-theoretic perspective on model interpretation. In *International Conference on Machine Learning*, pages 883–892. PMLR, 2018.

<a id="ref-6"></a>[6] Alexander Binder, Gregoire Montavon, Sebastian Lapuschkin, Klaus-Robert Müller, and Wojciech Samek. Layer-wise relevance propagation for neural networks with local renormalization layers. In *International Conference on Artificial Neural Networks*, pages 63–71. Springer, 2016.

<a id="ref-7"></a>[7] Daniel Smilkov, Nikhil Thorat, Been Kim, Fernanda Viégas, and Martin Wattenberg. SmoothGrad: Removing noise by adding noise. *arXiv preprint arXiv:1706.03825*, 2017.

<a id="ref-8"></a>[8] Mukund Sundararajan, Ankur Taly, and Qiqi Yan. Axiomatic attribution for deep networks. In *International Conference on Machine Learning*, pages 3319–3328. PMLR, 2017.

<a id="ref-9"></a>[9] Avanti Shrikumar, Peyton Greenside, and Anshul Kundaje. Learning important features through propagating activation differences. In *International Conference on Machine Learning*, pages 3145–3153. PMLR, 2017.

<a id="ref-10"></a>[10] Ramprasaath R. Selvaraju, Michael Cogswell, Abhishek Das, Ramakrishna Vedantam, Devi Parikh, and Dhruv Batra. Grad-CAM: Visual explanations from deep networks via gradient-based localization. In *Proceedings of the IEEE International Conference on Computer Vision*, pages 618–626, 2017.

<a id="ref-11"></a>[11] Aditya Chattopadhay, Anirban Sarkar, Prantik Howlader, and Vineeth N. Balasubramanian. Grad-CAM++: Generalized gradient-based visual explanations for deep convolutional networks. In *2018 IEEE Winter Conference on Applications of Computer Vision (WACV)*, pages 839–847. IEEE, 2018.

<a id="ref-12"></a>[12] Andrei Kapishnikov, Tolga Bolukbasi, Fernanda Viégas, and Michael Terry. XRAI: Better attributions through regions. In *Proceedings of the IEEE/CVF International Conference on Computer Vision*, pages 4948–4957, 2019.

<a id="ref-13"></a>[13] Samira Abnar and Willem Zuidema. Quantifying attention flow in transformers. In *Proceedings of the 58th Annual Meeting of the Association for Computational Linguistics*, pages 4190–4197, 2020.

<a id="ref-14"></a>[14] Hila Chefer, Shir Gur, and Lior Wolf. Transformer interpretability beyond attention visualization. In *Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition*, pages 782–791, 2021.

<a id="ref-15"></a>[15] Been Kim, Martin Wattenberg, Justin Gilmer, Carrie Cai, James Wexler, Fernanda Viégas, et al. Interpretability beyond feature attribution: Quantitative testing with concept activation vectors (TCAV). In *International Conference on Machine Learning*, pages 2668–2677. PMLR, 2018.

<a id="ref-16"></a>[16] Amirata Ghorbani, James Wexler, James Y. Zou, and Been Kim. Towards automatic concept-based explanations. *Advances in Neural Information Processing Systems*, 32, 2019.

<a id="ref-17"></a>[17] Dipkamal Bhusal, Michael Clifford, Sara Rampazzi, and Nidhi Rastogi. FACE: Faithful automatic concept extraction. *Advances in Neural Information Processing Systems*, 39, 2025.

<a id="ref-18"></a>[18] Quanshi Zhang, Ying Nian Wu, and Song-Chun Zhu. Interpretable convolutional neural networks. In *Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition*, pages 8827–8836, 2018.

<a id="ref-19"></a>[19] David Alvarez Melis and Tommi Jaakkola. Towards robust interpretability with self-explaining neural networks. *Advances in Neural Information Processing Systems*, 31, 2018.

<a id="ref-20"></a>[20] Quanshi Zhang, Yu Yang, Haotian Ma, and Ying Nian Wu. Interpreting CNNs via decision trees. In *Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition*, pages 6261–6270, 2019.

<a id="ref-21"></a>[21] Yash Goyal, Amir Feder, Uri Shalit, and Been Kim. Explaining classifiers with causal concept effect (CACE). *arXiv preprint arXiv:1907.07165*, 2019.

<a id="ref-22"></a>[22] Chih-Kuan Yeh, Been Kim, Sercan Arik, Chun-Liang Li, Tomas Pfister, and Pradeep Ravikumar. On completeness-aware concept-based explanations in deep neural networks. *Advances in Neural Information Processing Systems*, 33:20554–20565, 2020.

<a id="ref-23"></a>[23] Zhi Chen, Yijie Bei, and Cynthia Rudin. Concept whitening for interpretable image recognition. *Nature Machine Intelligence*, 2(12):772–782, 2020.

<a id="ref-24"></a>[24] Pang Wei Koh, Thao Nguyen, Yew Siang Tang, Stephen Mussmann, Emma Pierson, Been Kim, and Percy Liang. Concept bottleneck models. In *International Conference on Machine Learning*, pages 5338–5348. PMLR, 2020.

<a id="ref-25"></a>[25] Mateo Espinosa Zarlenga, Pietro Barbiero, Gabriele Ciravegna, Giuseppe Marra, Francesco Giannini, Michelangelo Diligenti, Zohreh Shams, Frederic Precioso, Stefano Melacci, Adrian Weller, et al. Concept embedding models: Beyond the accuracy-explainability trade-off. *Advances in Neural Information Processing Systems*, 35:21400–21413, 2022.

<a id="ref-26"></a>[26] Been Kim, Rajiv Khanna, and Oluwasanmi O. Koyejo. Examples are not enough, learn to criticize! Criticism for interpretability. *Advances in Neural Information Processing Systems*, 29, 2016.

<a id="ref-27"></a>[27] Pang Wei Koh and Percy Liang. Understanding black-box predictions via influence functions. In *International Conference on Machine Learning*, pages 1885–1894. PMLR, 2017.

<a id="ref-28"></a>[28] Chih-Kuan Yeh, Joon Kim, Ian En-Hsu Yen, and Pradeep K. Ravikumar. Representer point selection for explaining deep neural networks. *Advances in Neural Information Processing Systems*, 31, 2018.

<a id="ref-29"></a>[29] Garima Pruthi, Frederick Liu, Satyen Kale, and Mukund Sundararajan. Estimating training data influence by tracing gradient descent. *Advances in Neural Information Processing Systems*, 33:19920–19930, 2020.

<a id="ref-30"></a>[30] Chaofan Chen, Oscar Li, Daniel Tao, Alina Barnett, Cynthia Rudin, and Jonathan K. Su. This looks like that: Deep learning for interpretable image recognition. *Advances in Neural Information Processing Systems*, 33, 2019.

<a id="ref-31"></a>[31] Meike Nauta, Ron Van Bree, and Christin Seifert. Neural prototype trees for interpretable fine-grained image recognition. In *Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition*, pages 14933–14943, 2021.

<a id="ref-32"></a>[32] Rose Gurung, Ronilo Ragodos, Chiyu Ma, Tong Wang, and Chaofan Chen. ProtoPairNet: Interpretable regression through prototypical pair reasoning. *Advances in Neural Information Processing Systems*, 39, 2025.

<a id="ref-33"></a>[33] Sangwon Kim, Jaeyeal Nam, and Byoung Chul Ko. ViT-NeT: Interpretable vision transformers with neural tree decoder. In *International Conference on Machine Learning*, pages 11162–11172. PMLR, 2022.

<a id="ref-34"></a>[34] Amit Dhurandhar, Pin-Yu Chen, Ronny Luss, Chun-Chen Tu, Paishun Ting, Karthikeyan Shanmugam, and Payel Das. Explanations based on the missing: Towards contrastive explanations with pertinent negatives. *Advances in Neural Information Processing Systems*, 31, 2018.

<a id="ref-35"></a>[35] Yash Goyal, Ziyan Wu, Jan Ernst, Dhruv Batra, Devi Parikh, and Stefan Lee. Counterfactual visual explanations. In *International Conference on Machine Learning*, pages 2376–2384. PMLR, 2019.

<a id="ref-36"></a>[36] Riccardo Guidotti, Anna Monreale, Stan Matwin, and Dino Pedreschi. Black box explanation by learning image exemplars in the latent feature space. In *Joint European Conference on Machine Learning and Knowledge Discovery in Databases*, pages 189–205. Springer, 2019.

<a id="ref-37"></a>[37] Arnaud Van Looveren and Janis Klaise. Interpretable counterfactual explanations guided by prototypes. In *Joint European Conference on Machine Learning and Knowledge Discovery in Databases*, pages 650–665. Springer, 2021.

<a id="ref-38"></a>[38] Silvan Mertes, Tobias Huber, Katharina Weitz, Alexander Heimerl, and Elisabeth André. GANterfactual—counterfactual explanations for medical non-experts using generative adversarial learning. *Frontiers in Artificial Intelligence*, 5:825565, 2022.

<a id="ref-39"></a>[39] Guillaume Jeanneret, Loïc Simon, and Frédéric Jurie. Diffusion models for counterfactual explanations. In *Proceedings of the Asian Conference on Computer Vision*, pages 858–876, 2022.

<a id="ref-40"></a>[40] Dong Huk Park, Lisa Anne Hendricks, Zeynep Akata, Anna Rohrbach, Bernt Schiele, Trevor Darrell, and Marcus Rohrbach. Multimodal explanations: Justifying decisions and pointing to the evidence. In *Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition*, pages 8779–8788, 2018.

<a id="ref-41"></a>[41] Jialin Wu and Raymond Mooney. Faithful multimodal explanation for visual question answering. In *Proceedings of the 2019 ACL Workshop BlackboxNLP: Analyzing and Interpreting Neural Networks for NLP*, pages 103–112, 2019.

<a id="ref-42"></a>[42] Ge Zheng, Bin Yang, Jiajin Tang, Hong-Yu Zhou, and Sibei Yang. DDCoT: Duty-distinct chain-of-thought prompting for multimodal reasoning in language models. *Advances in Neural Information Processing Systems*, 36:5168–5191, 2023.

<a id="ref-43"></a>[43] Xu Ma, Yuqian Zhou, Huan Wang, Can Qin, Bin Sun, Chang Liu, and Yun Fu. Image as set of points. *arXiv preprint arXiv:2303.01494*, 2023.

<a id="ref-44"></a>[44] Guikun Chen, Xia Li, Yi Yang, and Wenguan Wang. Neural clustering based visual representation learning. In *Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition*, pages 5714–5725, 2024.

---

This repository is inspired and grounded in the following surveys:

<a id="ref-s1"></a>
[S1] Francesco Bodria, Fosca Giannotti, Riccardo Guidotti, Francesca Naretto, Dino Pedreschi, and Salvatore Rinzivillo. Benchmarking and survey of explanation methods for black box models. Data Mining and Knowledge Discovery, 37(5):1719–1778, 2023.

<a id="ref-s2"></a>
[S2] Zhihan Cheng, Yue Wu, Yule Li, Lingfeng Cai, and Baha Ihnaini. A comprehensive review of explainable artificial intelligence (XAI) in computer vision. Sensors, 25(13):4166, 2025.

<a id="ref-s3"></a>
[S3] Rémi Kazmierczak, Eloïse Berthier, Goran Frehse, and Gianni Franchi. Explainability for vision foundation models: A survey. arXiv preprint arXiv:2501.12203, 2025.
