# SooperGAN
Study GAN with toyproblems

// 2021 07 19 GAN studty
Taxonomy of Generative Models

- Explicit Density
  - Trackable Density (정의할 수 있는 모수함수가 있을 경우) : PixelCNNS
  - Approximate Density (문제정의가 너무 복잡하여 모수함수를 정할 수 없으므로, 분포를 추정) : VAEs

- Implicit Density
  - Implicit Density (밀도를 명시적으로 모델링하지 않고 관찰된 변수를 바탕으로 매핑) : GAN
  
Generative Adverserial Network 에서
Nash Equilibrium 을 이루기 위해 각 플레이어의 비용함수 합을 1로 맞춰나감.

1단계: Generator를 통해 Fake 분포를 만들고, 실제 분포와의 오차를 계산하는 비용함수를 사용해 Discriminator를 학습한다.
    이 때, Generator의 가중치가 아닌, Discrminator의 가중치 만을 수정한다.
2단계: Genrator가 만든 Fake 분포에 True Label을 주고 Discriminator의 오류를 최대화 하는 방향으로 학습하되,
    이 때, 갱신되는 가중치는 Generator에서만 수정한다.
