<a>Video Ref : https://www.youtube.com/watch?v=nvg0L0c0iPI&t=24997s</a>

<h1>The Viola_johns Algorithm</h1>
<p>Includes training & detection(same as training and prediction)
This algorithm is designed to detect frontal faces. 
Gray-scale (less data, easier to process)
Scan the similar sequence of CNN, Look for feature of face.
</p>

<a>http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.10.6807&rep=rep1&type=pdf</a>

<h3>Haar-Like Features</h1>
<p>Edge Features.Line Features . Four-rectangle Features. </p>
<p>each block of image array is compared with features mentioned above.
eg, if nose is trained to have such a pattern. The algorithm will look for that pattern. and a threshold is set to decide what an array need to be to be classified as such feature.</p>
                                                                                                   
<h3>Integral Image</h1>                                                                               
<p>speed up the feature scanning, number on each pixel equal to the sum of all the number in the rectangle of <----x axis and ^ y axis./p>
