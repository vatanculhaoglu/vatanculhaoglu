# Vatan Çulhaoğlu

**Computer vision and applied machine learning.**

Final-year software engineering student at Istanbul Aydın University, on a full scholarship,
back from an Erasmus+ exchange year at Kaunas University of Technology on an AI-focused
curriculum. I build real-time computer vision systems and ship cross-platform products — and
I measure both.

[Portfolio](https://vatanculhaoglu.vercel.app) ·
[LinkedIn](https://www.linkedin.com/in/vatan-%C3%A7ulhao%C4%9Flu-bb3209319/) ·
vatanculhaoglu1@gmail.com

---

## What I am working on

### AeroSAR — real-time aerial search-and-rescue detection

Graduation project. Person detection in drone imagery, with two operating modes: unsliced
YOLO with ByteTrack for live awareness during flight, and SAHI sliced inference with BoT-SORT
for close inspection of a suspected area.

It runs at **29.5 FPS end to end on 1080p@30 video** (RTX 2060), up from 19.6 after I profiled
the bottleneck to the tracker's camera-motion compensation (~36 ms/frame) and switched tracker.
Detection quality is **mAP50 0.850 / recall 0.858 on HERIDAL** and **0.951 / 0.966 on SARD**.
Mid-project I audited the training data, found the negative ratio was 54.5% rather than the
assumed 15%, and dropped two datasets that failed validation.

`Python` `Ultralytics YOLO` `SAHI` `ByteTrack` `BoT-SORT` `OpenCV` `Weights & Biases`

### TESTO — cross-platform fitness and nutrition application

Built alone: a 58-endpoint REST API on Express and MySQL, an Expo/React Native client for iOS
and Android, and a framework-free web client over the same backend — **30,425 lines across 15
database tables and 12 mobile screens in four months.**

The part I care about is translating published sports-science formulas into production
algorithms. The nutrition engine chooses between Katch-McArdle and Mifflin-St Jeor depending on
the body-composition data available, then self-corrects its calorie target from actual weekly
weight change, with a floor that prevents unsafe deficits. The training side derives the next
target from set performance and recommends recovery instead of pushing when the user regresses.

Deployed on Railway with seven endpoint-specific rate limiters, TOTP two-factor authentication
and Keychain/Keystore token storage. Google Play closed testing completed; submitted to App
Store review. Awarded 10/10 at the university project defence.

`TypeScript` `React Native` `Expo` `Node.js` `Express` `MySQL` `Railway`

> Every figure above comes from these projects' own benchmark runs and code counts — not from
> an independent benchmark.

---

## Why most of these repositories are private

AeroSAR is a graduation project that has not been submitted yet, and TESTO is a product
currently in store review, so both stay closed for now.

The [portfolio site](https://vatanculhaoglu.vercel.app) covers them properly instead:
architecture diagrams of how each system works, what I specifically did, the measurements, and
where each number comes from. [`portfolio`](https://github.com/vatanculhaoglu/portfolio) is
public — it is that site's own source, and the one repository here you can read end to end.

---

## From the exchange year at KTU

- **One workload, three parallelism models.** The same 500,000-record scoring workload solved
  three ways and compared: a hand-written bounded-buffer monitor with condition variables
  (threads), a 12-tag message protocol over MPI with custom derived datatypes built through
  `MPI_Type_create_struct` (processes), and CUDA kernels with warp-aligned block sizes and
  grid-stride execution.
- **Machine learning from scratch.** Decision trees, random forests and a feed-forward network
  with backpropagation implemented without libraries, then 18 architecture/activation
  combinations trained and benchmarked against scikit-learn.
- **Traffic video analysis.** YOLOv8 with ByteTrack for persistent vehicle IDs, plus a motion
  classifier that labels each tracked vehicle from its centre-point history; custom detection
  and segmentation pipelines trained alongside.

---

## Tools

| Area | Stack |
|---|---|
| **AI & vision** | Python · Ultralytics YOLO · SAHI · ByteTrack · BoT-SORT · OpenCV · PyTorch · TensorFlow/Keras · scikit-learn · NumPy · pandas · FiftyOne · Weights & Biases · MATLAB |
| **Parallel & systems** | C++17 · OpenMP · MPI · CUDA · Linux · Bash |
| **Backend & data** | Node.js · Express · MySQL · REST API design · JWT · TOTP · SQL · Flask · SQLAlchemy · R |
| **Mobile & web** | React Native · Expo · TypeScript · React · Next.js · Tailwind CSS |
| **Delivery** | Git · Railway · Vercel · Google Play Console · App Store Connect · UML (MagicDraw) |

---

Next step is an MSc in Artificial Intelligence in Computer Science. Seeking an internship or a
role in AI and software engineering — [get in touch](mailto:vatanculhaoglu1@gmail.com).
