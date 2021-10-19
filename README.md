# MOE
## OUTRAGEOUSLY LARGE NEURAL NETWORKS:THE SPARSELY-GATED MIXTURE-OF-EXPERTS LAYER
This paper introduced a the general idea of MOE in NLP.
The concept is simple to understand with expert and gating network in MOE.
<img width="677" alt="Screen Shot 2021-10-19 at 1 41 33 PM" src="https://user-images.githubusercontent.com/42342410/137962894-25b370f4-c463-41a9-944f-161ed7203577.png">
As you can see in the picture, it is a standard LSTM picture with a MOE layer.

## SPMoE: Generate Multiple Pattern-Aware Outputs with Sparse Pattern Mixture of Experts
This paper introduced the sparse MOE which is a novel concept.

<img width="397" alt="Screen Shot 2021-10-19 at 1 45 40 PM" src="https://user-images.githubusercontent.com/42342410/137963376-f3462039-b3c0-4b21-9185-1782997da45a.png">

For a input ouput pair set C={(x1,y1),(x2,y2),(x3,y3)...}. x is input source set, y is translation set. K is generated pattern which one to one map x to y. The target is automatically extract pattern and generate the output translation.

<img width="165" alt="Screen Shot 2021-10-19 at 1 50 45 PM" src="https://user-images.githubusercontent.com/42342410/137964128-2dc91069-b1f3-404c-ae71-6bd450a8d331.png">

The back- bone of SPMoE is a transformer-based model which can be easily adapted from pre-trained language models like BART. All expert models in SPMoE share the same backbone structure while their pattern heads are separate and are implemented with a linear layer. All the pattern heads are coordinated with a sparse mecha- nism and a load balance strategy to enforce each expert model to be as distinct as possible. Specifically, the backbone is used for a better representation of the source-target pairs while the sparse mechanism is used to allocate these pairs into different patterns.

## SPARSE MOES MEET EFFICIENT ENSEMBLES
This paper introduced two different approach with ensembles of CNN and Sparse of MOE.

<img width="613" alt="Screen Shot 2021-10-19 at 1 57 45 PM" src="https://user-images.githubusercontent.com/42342410/137965086-1a255d03-88bb-420c-9a44-19ae7f7e0b16.png">

This paper introduced the Complementarity of MoEs and ensembles. They show that sparse MoEs and enembles have complementary features and benefit from each other. The adaptive computation in sparse MoEs and the static combination in ensembles are orthogonal, with additive benefits when associated together. Their association results in insightful performance versus FLOPs trade-offs while varying the ensemble size and sparsity. In sparse MoEs, combining models at the prediction level leads to improved uncertainty estimates. Over tasks where either sparse MoEs or ensembles are known to perform well, naive—and com- putationally expensive—ensembles of MoEs provide the best predictive performance.

This paper also intriduced the Partitioned batch ensembles. pBE improves over sparse MoEs across metrics including few-shot performance, likelihood and calibration error. pBE matches the performance of deep ensembles for 30%-43% fewer FLOPs. pBE is both simple (requiring only minor implementation changes) and convenient because standard sparse-MoE checkpoints can be used directly to initialize pBEs for fine-tuning.
