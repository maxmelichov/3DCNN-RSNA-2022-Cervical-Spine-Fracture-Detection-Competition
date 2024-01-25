# 3DCNN-RSNA-2022-Cervical-Spine-Fracture-Detection-Competition

## Goal of the Competition

The goal of this competition is to explore whether artificial intelligence can be used to aid in the detection and localization of cervical spine fractures. With over 1.5 million spine fractures occurring annually in the United States alone, it is crucial to quickly detect and determine the location of vertebral fractures to prevent neurologic deterioration and paralysis after trauma.

## Context

RSNA has partnered with the American Society of Neuroradiology (ASNR) and the American Society of Spine Radiology (ASSR) to conduct this AI challenge competition. The challenge planning task force collected imaging data from twelve sites on six continents, including approximately 3,000 CT studies, to create the ground truth dataset. Expert image level annotations were provided by spine radiology specialists to indicate the presence, vertebral level, and location of any cervical spine fractures.

## Competition Details

In this challenge, participants are required to develop machine learning models that can match the performance of radiologists in detecting and localizing fractures in the seven vertebrae of the cervical spine (C1, C2, C3, C4, C5, C6, and C7). Submissions are evaluated using a weighted multi-label logarithmic loss. Each fracture subtype is considered as a separate row for every exam, and participants are expected to predict the probability of a fracture at each cervical vertebra. The "any" label indicates the presence of any kind of fracture in the examination and is weighted more highly than specific fracture level subtypes.

## Submission Format

For each exam ID, participants must submit a set of predicted probabilities for each cervical level subtype. The log loss is calculated for each predicted probability versus its true label, and the final loss is averaged across all rows. The submission file should contain a header and follow the specified format.

For more information on the challenge, please contact RSNA Informatics staff at informatics@rsna.org.

A full set of acknowledgments can be found on the competition page.

[https://github.com/maxmelichov/3DCNN-RSNA-2022-Cervical-Spine-Fracture-Detection-Competition/blob/main/128b.gif]