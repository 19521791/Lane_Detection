<h1 align="center">LANE DETECTION</h1>
<h3>Link source code if file Lane_Detection_Using_CNN not working <a target="_blank" href="https://colab.research.google.com/drive/1KQSA2xzih-2y9gdFWtRf9L-Pj4Y8BiFS?usp=sharing">Here</a></h3>
<h2>Introduction</h2>
<p>Lane detection is an important component of autonomous vehicle systems. Highway lane departure warning solutions have been on the market since the mid-1990s. However, improving and generalizing computer vision-based lane detection capabilities remains a challenge. A challenging and difficult task until recently.</p>
<p>CNN - Convolutional Neural Network, also known as the convolutional neural network, is one of the advanced and widely used Deep Learning models in image and video processing problems. </p>
<h2>Methods</h2>
<h3>Network Architecture</h3>
<p align="center">
<img width="800" height="300" src="network-arc.png">
</p>
<ul>
  <li><b>Input</b>: An image (80, 160, 3).</li>
  <li><b>Output</b>: A binary mask.</li>
</ul>
<h3>Dataset</h3>
<h4>Images</h4>
<p align="center">
  <img width="600" height="250" src="image.png">
</p>
<h4>Labels</h4>
<p align="center">
  <img width="600" height="250" src="label.png">
</p>
<h3>Layers</h3>
<ul>
  <li><b>Convolution</b>
    <ul>
      <li>Input: A tensor</li>
      <li>Purpose: Extract feature</li>
      <li> How it works:
        <ul>
          <li>An image matrix (volume) of dimension <b>(h x w x d)</b></li>
          <li>A filter <b>(f<sub>h</sub> x f<sub>w</sub> x d)</b></li>
          <li>Outputs a volume dimension <b>(h - f<sub>h</sub> + 1) x (w -  f<sub>w</sub> + 1) x 1)</b></li>
        </ul>
      </li>
      <li>Output: A feature map</li>
    </ul>
  </li>
  <li><b>MaxPooling2D</b>
    <ul>
      <li>Input: A tensor</li>
       <li>Purpose: Reduce input size</li>
      <li>Output: A tensor</li>
    </ul>
  </li>
  <li><b>Dropout</b>
    <ul>
      <li>Input: A tensor</li>
      <li>Purpose: Reduce computing</li>
      <li>Output: A tensor</li>
    </ul>
  </li>
  <li><b>Upsample</b>
    <ul>
      <li>Input: A tensor</li>
      <li>Purpose: Increase output size</li>
      <li>Output: A tensor</li>
    </ul>
  </li>
  <li><b>Conv2Dtranspose</b>
    <ul>
      <li>Input: A tensor</li>
       <li>Purpose: Increase output size</li>
      <li>Output: A tensor</li>
    </ul>
  </li>
</ul>
<h2>Results</h2>
<h3>Metrics</h3>
<p>After 10 times of training with batch size 128, the model ends with MSE for training is 0.0077 and validation is 0.0072.</p>
<p align="center">
  <img width="600" height="250" src="batch128.png">
</p>
<p align="center">
  <img width="600" height="250" src="result-128.png">
</p>
<ul>
  <li><b>Accuracy</b>: 97.79%</li>
  <li><b>Precision</b>: 98%</li>
  <li><b>Recall</b>: 89%</li>
  <li><b>F1-score</b>: 93%</li>
  <li><b>IoU</b>: 87%</li>
</ul>
<h3>Tuning hyperparameter</h3>
<h4>Batch size 128 -> 64</h4>
<p>the MSE for training and validation: 0.0059 and 0.0045.</p>
<p align="center">
  <img width="600" height="250" src="batch64.png">
</p>
<h4>
<h4>Batch size 64 -> 32</h4>
<p>the MSE for training and validation: 0.0052 and 0.0043.</p>
<p align="center">
  <img width="600" height="250" src="batch32.png">
</p>
<h4>
<h3>Video demo</h3>
<p align="center">
<img src="https://user-images.githubusercontent.com/79817900/211891175-b14a5782-5eee-41da-8212-b1050c3d848f.gif">
</p>
<p>One of the most beautiful roads in Vietnam, it is located next to Phan Thiet beach, Binh Thuan province.</p>
<p>Link input video: <a target="_blank" href="https://www.youtube.com/watch?v=rOFo-bnWA9Q&t=2399s">from 31:37 to 31:47</a></p>
