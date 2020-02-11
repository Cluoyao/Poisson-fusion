#include <opencv2\opencv.hpp>
#include <iostream>
#include <string>

using namespace std;
using namespace cv;

void main()
{
	Mat src = imread("stich_imgs_1/final_img.jpg");
	Mat dst = imread("stich_imgs_1/final_img.jpg");
	//cv::namedWindow("dst", CV_WINDOW_NORMAL);
	//cv::imshow("dst", src);
	//waitKey(0);
	// Create a rough mask around the airplane.
	Mat src_mask = imread("stich_imgs_1/mul_inser_mask.jpg");
  
	// The location of the center of the src in the dst
	//Point center(1932.53, 905.521);
	Point center(1932.53, 905.521);
	cout << center.x << " " << center.y << endl;

	// Seamlessly clone src into dst and put the results in output
	Mat output;
	seamlessClone(src, dst, src_mask, center, output, NORMAL_CLONE);
	circle(src_mask, center, 5, Scalar(0, 0, 255), -1);
	namedWindow("center", CV_WINDOW_NORMAL);
	imshow("center", src_mask);
	waitKey(0);
	// Save result
	imwrite("stich_imgs_1/blended.jpg", output);
}
