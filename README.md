# Welcome to the Stroma's Machine Learning Engineering Challenge!
> The objective of this challenge project is for you to showcase your capabilities in creating neural network pipelines.

Your result should be able to predict and track the number of nuts and bolts that have fallen through the frame of the provided video snippets with high accuracy.

You are provided with 4 minutes of video for training and 2 minutes of video for validation and another 2 minutes of video for testing. The [video files](https://github.com/Stroma-Vision/machine-learning-challenge/releases/download/v0.1/challenge.zip) are synthetically generated 640x640 frames in 30FPS, each frame is accurately labeled in the [COCO](https://opencv.org/introduction-to-the-coco-dataset/) format with an additional field named `track_id`.

> Please review the [Challenge Instructions](https://stromavision.notion.site/Stroma-Machine-Learning-Engineer-Technical-Interview-19f4573982b64791b14121faddb2f176) once again before proceeding.

Image below shows the expected output of your model.

![Expected Output](./sample.gif)

## Data

**Folder Structure**
```bash
challenge
├── annotations
│   ├── instances_test.json
│   ├── instances_train.json
│   └── instances_val.json
└── images
    ├── test
    │   └── test.mp4
    ├── train
    │   └── train.mp4
    └── val
        └── val.mp4

6 directories, 6 files
```

Each annotation in COCO format contains a `track_id` section. With the following schema:

**JSON Schema**

```json
"annotations":[
    {
        "id": int,
        "image_id": int, (#frame)
        "category_id": int,
        "segmentation": RLE,
        "area": float,
        "bbox": [x,y,width,height],
        "iscrowd": 0,
        "track_id": int,
    },
    ...
]
```
You may use any type of model of your preference, if your model requires any other annotation format, be careful when converting dataset to your format.

## Results

You have the freedom to present your work in any format, and it will be evaluated based on the overall representation of your work. Utilizing visualizations is encouraged. However, keep in mind that your audience will be technical and familiar with the field, so a clear and concise explanation of your work is highly recommended.

⚠️Remember that the performance of your model will be evaluated using a separate validation dataset.

`Note: You may submit a Github repo with scripts or a google colab notebook with your work.`

## Suggestions

- Training a model from scratch may take a lot of time, you may use a `pretrained` model and fine-tune it to reach your goal.

- Optimize the dataset for the available hardware resources by either utilizing a `subset` to iterate faster or use `augmentation techniques` to improve your model's accuracy, as appropriate.

- Make sure to document your work, you may provide an explanatory `README.md` file or you may use `Jupyter Notebook`'s markdown cells to explain your findings.

- Please ensure to `document` any difficulties encountered and the corresponding resolution methods adopted during the completion of this challenge as they are of utmost relevance to us.
