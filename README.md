# Traffic Accident Classification Challenge

This challenge focuses on classifying traffic accident videos into different categories based on their characteristics. Participants are provided with a dataset of traffic accident videos and must develop a model to predict the accident category for each video.

## Dataset Structure

```
hackathon/
├── train/                  # Training set (210 videos)
│   ├── *.mp4              # Video files
│   └── train_videos.csv   # Annotations for training videos
├── test/                   # Testing set (90 videos)
│   ├── *.mp4              # Video files
│   └── test_videos.csv    # Annotations for testing videos
└── all_videos.csv         # Complete annotations for all videos
```

## Data Format

### Videos
- Format: MP4
- Naming: 6-digit numbers (e.g., 001234.mp4)

### CSV Files
Training data includes:
- `video_name`: Video file name (e.g., 001234.mp4)
- `accident_category`: Category label (1-10)
- `causes`: Description of the accident cause (categorical)
- `split`: Dataset split (train/test)

## Challenge Task

Develop a model to classify traffic accident videos into one of 10 categories. The model should be able to:
1. Process video input
2. Analyze accident characteristics
3. Predict the most likely accident category

## Submission Format

### CSV Submission
Submit a CSV file with the following columns:
- `video_name`: Name of the test video
- `accident_category`: Predicted category (1-10)
- `causes`: Predicted accident cause category

Example:
```csv
video_name,predicted_category
001234.mp4,3,Motorcyclist fails to observe surrounding traffic during maneuvers
001235.mp4,7,Two-wheeler violates traffic signal
...
```

## Evaluation

### Metrics
- Primary metric: Macro F1-score
- Performance will be evaluated on the test set
- Submissions must include predictions for all test videos

### Evaluation Script
We provide a Python script (`evaluate.py`) to calculate:
- Macro F1-score
- Per-category precision, recall, and F1-scores
- Support for each category

Usage:
```bash
python evaluate.py submission.csv ground_truth.csv
```

## Dataset Statistics
- Total videos: 300
- Training set: 210 videos (70%)
- Testing set: 90 videos (30%)
- Categories: 10 distinct accident types

## Rules
1. Only use provided training data
2. No manual labeling of test data
3. Top performers may be required to submit code for verification
4. One submission per day per team
5. Final rankings will be based on test set performance

## Submission Checklist
- [ ] CSV file with predictions for all test videos
- [ ] Correct format (video_name, predicted_category)
- [ ] Values within valid range (1-10)
- [ ] No missing predictions
