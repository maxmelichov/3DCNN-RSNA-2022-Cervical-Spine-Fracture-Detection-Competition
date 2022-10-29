# 3DCNN-RSNA-2022-Cervical-Spine-Fracture-Detection-Competition
Goal of the Competition
Over 1.5 million spine fractures occur annually in the United States alone resulting in over 17,730 spinal cord injuries annually. The most common site of spine fracture is the cervical spine. There has been a rise in the incidence of spinal fractures in the elderly and in this population, fractures can be more difficult to detect on imaging due to superimposed degenerative disease and osteoporosis. Imaging diagnosis of adult spine fractures is now almost exclusively performed with computed tomography (CT) instead of radiographs (x-rays). Quickly detecting and determining the location of any vertebral fractures is essential to prevent neurologic deterioration and paralysis after trauma.

Context
RSNA has teamed with the American Society of Neuroradiology (ASNR) and the American Society of Spine Radiology (ASSR) to conduct an AI challenge competition exploring whether artificial intelligence can be used to aid in the detection and localization of cervical spine fractures.

To create the ground truth dataset, the challenge planning task force collected imaging data sourced from twelve sites on six continents, including approximately 3,000 CT studies. Spine radiology specialists from the ASNR and ASSR provided expert image level annotations these studies to indicate the presence, vertebral level and location of any cervical spine fractures.

In this challenge competition, you will try to develop machine learning models that match the radiologists' performance in detecting and localizing fractures to the seven vertebrae that comprise the cervical spine. Winners will be recognized at an event during the RSNA 2022 annual meeting.

For more information on the challenge, contact RSNA Informatics staff at informatics@rsna.org.

A full set of acknowledgments can be found on this page.

Submissions are evaluated using a weighted multi-label logarithmic loss. Each fracture sub-type is its own row for every exam, and you are expected to predict a probability for a fracture at each of the seven cervical vertebrae designated as C1, C2, C3, C4, C5, C6 and C7. There is also an any label, patient_overall, which indicates that a fracture of ANY kind described before exists in the examination. Fractures in the skull base, thoracic spine, ribs, and clavicles are ignored. The any label is weighted more highly than specific fracture level sub-types.

For each exam Id, you must submit a set of predicted probabilities (a separate row for each cervical level subtype). We then take the log loss for each predicted probability versus its true label.

The binary weighted log loss function for label j on exam i is specified as:
Lij=−wj∗[yij∗log(pij)+(1−yij)∗log(1−pij)]
Finally, loss is averaged across all rows.

There will be 8 rows per image Id. The label indicated by a particular row will look like [image Id]_[Sub-type Name], as follows. There is also a target column, fractured, indicating the probability of whether a fracture exists at the specified level. For each image ID in the test set, you must predict a probability for each of the different possible sub-types and the patient overall. The file should contain a header and have the following format:
