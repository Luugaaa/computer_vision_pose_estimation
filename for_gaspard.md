Hey Paul! It looks like you've made some really solid progress on TP3. Your pipeline for loading the dataset, running inference with SimpleHRNet, and calculating the MPJPE and PCK metrics across the different activity categories is looking great!

Looking at your notebook code and comparing it strictly to the technical and coding requirements in the assignment instructions, there are a couple of implementation steps missing that you'll need to add to generate the required outputs for your report:

Extracting the Worst-Case Sample: Your code calculates the overall metrics, but it doesn't specifically isolate the single sample with the lowest overall accuracy. You need to identify this exact image and its activity category.

Overlaying Ground-Truth and Predictions: For that worst-case image, you need to generate a visualization that overlays both the predicted pose and the ground-truth pose on the same image. Currently, your plot_mpii_people function only plots the predictions. You'll want to modify it (or add a new function) to plot the gt_xy coordinates alongside the people_xy predictions.

Extracting 5 Failure Cases: You need to isolate and plot at least 5 diverse examples where your model fails. Your current loop processes all 750 images but doesn't save or display the specific images where the estimation completely broke down. You could easily tweak your loop to save images where the MPJPE is unusually high or the PCK is very low.

One quick non-code heads-up:
While the instructions explicitly state that you are free to choose any 2D pose estimation model , they also specifically suggest looking at the MMPose library as a starting point. Since you opted for SimpleHRNet, just make absolutely sure you heavily justify this model choice in your report as required.
+1

You're super close! Just a few tweaks to your evaluation loop to save those specific edge-case images and you'll have everything you need.