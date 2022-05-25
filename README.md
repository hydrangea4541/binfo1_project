# binfo1_project
Bioinformatics 1 class project (2022-spring)

자유 프로젝트 주제 by. 김준식

# 지정 과제
(★) Fig S3C 재현해보기 - transcriptome에서 error가 많이 나오는 부분들 주변 서열을 모아서 문맥을 파악합니다.

Fig S3. Identification of LIN28A Binding Sites, related to Fig 2.
  
(C) Consensus of confident binding sites from individual CLIP-seq libraries

# 개요
해당 부분의 본문 내용: LIN28A Favors Single-Stranded Purine-Rich Motifs
- LIN28A-RNA interaction에 대한 이해 증진을 위함
- 이를 위해 LIN28A binding site 후보지의 pattern을 파악함(Fig 2A, S3C)
- 결과: 
  CLIP-seq로 인해 frequently mutated되는 G가 있고, 이 부분이 LIN28A binding motif(DNA)로 추정.  
  해당 위치의 G의 upstream에 2 base(A & U)를 선호하도록 변이 잦음 & 그 다음으로는 3 base(A & G)
  이는 해당 구간에서 가장 자주 발견되는 변이 hexamer인 'AAGGAG'와 차이가 있는 경향.
- 이 결과가 연구 상 필요했던 이유, 그리고 이 결과를 통한 다음 과정 소개하는 방식으로 발표 진행

# 스토리라인
해당 내용을 토대로 분석 및 최종 발표 진행

## 서론
- CLIP-seq로 LIN28A-RNA complex를 형성, LIN28A의 binding motif에 대한 특징을 알아낼 수 있었음.
  * 이 complex를 IP하기 위해 anti-LIN28A antibody 3가지를 이용해 library 3가지 구축
  * (Rb)Polyclonal antibody, (M) monoclonal antibody(35L33G, 2J3)
  * 이 IP를 LIN28A가 없을 때 사용할 떄와 비교했을 떄, LIN28A가 있으면 더 많이 검출 -> LIN28A의 특정적인 IP 성공
  * (Q) polyclonal은 왜 사용? 특정적인 IP를 원하는데...
- CLIP-seq로 인해 frequently mutated되는 G가 있고, 이 부분이 LIN28A binding motif(DNA)로 추정.  
- 이전 연구(Heo et al., 2009)에서 let-7 precursor의 terminal loop에서 GGAG motif가 zinc finger domain(CCHC)의 binding center임을 밝힘
- CLIP tag에서 GGAG motif에 자주 변이가 있었음을 확인: CLIP-seq의 특징으로 인해! 특히 motif의 첫 G가 자주 변이함. 
- non-miRNA transcripts에 대한 mapping tag가 많음: LIN28A - let7g 이외의 interaction 기대 가능
- (Q) 기존 let7g에서만 발견했던 패턴을 transcript에서도 발견한 것? + 이 주변의 sequence 패턴을 확인하여 transcriptome에서 LIN28A가 어떻게 작용하는지 확인하는 것?


## 목표 1(minimum)
1. Fig S3C를 재현: Error-prone region의 WebLogo image 그리기
- 대상: Three biological replicates of LIN28A binding motif
        (35L33G, 2J3, Polyclonal)
- https://weblogo.berkeley.edu/examples.html#splice
2. 결과의 문맥 파악
(Q) '문맥'이라 함은 어떤 패턴의 sequence가 가장 많이 발견되는지에 대한 질문인가?

## 목표 2(Extended)
1. Fig 2A 재현
- 3가지 biological replicate에 대해 진행한 Fig S3C와 달리, 모든 replicate를 통합하여 만든 WebLogo image로 추정됨.
  목표 1을 통합하여 만들면 되는 것 같음. 
2. Fig 2B 재현
- LIN28A-interacting hexamer 나열 및 frequency 보고
  (Q) 이것이 Fig 2A, S3C와 어떻게 비교된 것인지. 구체적으로 2A와 '뭘' 비교하고 다음으로 넘어간 것인가? 'most frequently observed hexamer'란 어디서 관찰된 것을 지칭하는가?
3. Fig 2C 재현
- (Q) 주변 hairpin을 구성하는 flanking hexamer 같음. 맞는지?

## 분석에 필요한 파일
(Q) 리스트 뽑아보고, 맞는지 질문 드리기.

## 결론
(분석으로 도출한 '결과의 문맥'을 여기에 적으면 됨.)

## 이후 분석
- 이전에 가지고 있던, 'most frequently observed hexamer' 패턴과 다른 경향을 보인 것을 토대로 함.
- consensus는 사실 multiple distinct motif의 혼합으로 추정, cluster 3개를 파악. (AAGNNG, AAGNG(N),(N)UGUG(N))
- AAGNNG: LIN28A binding site 중 2개의 zinc finger motif가 AGNNG를 인식한다는 연구(Loughlin et al., 2012)와 일맥 상통
- UGUG: 기존에 report되지 않은 motif - 기존에 발견되지 않은 LIN28A binding을 보고할 수도 있음.
- 이에 따라 EMSA 진행, LIN28A의 새로운 binder를 발견. 

- 즉, CLIP-seq를 통해 실제로 RNA와 protein의 interaction을 유발하고 관찰하니, 이전 연구에서 본 적 없는 새로운 cluster를 발견하게 됨. 
