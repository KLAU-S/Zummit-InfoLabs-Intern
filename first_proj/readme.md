# Age and Gender Detection

A machine learning model that can predict a person's age and gender from a single image or video. The project is divided into two parts:

1. **Part 1**: A model trained on the UTKFace dataset, which consists of over 20,000 images of faces labeled with age and gender. This model uses deep learning techniques to extract features from the images and make accurate predictions.
![1st part of the project](https://github.com/KLAU-S/Zummit-InfoLabs-Intern/blob/master/first_proj/misc/first.png)

2. **Part 2**: A real-time implementation of the model using a webcam or video feed. The model is trained on the same dataset as Part 1 and uses the same techniques, but it is optimized for real-time performance.
![2nd part of the project](https://github.com/KLAU-S/Zummit-InfoLabs-Intern/blob/master/first_proj/misc/second.png)
## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites

To run this project, you will need the following software and libraries:

- Python 3.6 or higher
- NumPy
- Pandas
- TensorFlow
- Keras
- OpenCV (for Part 2 only)

### Installing

1. Create a Virtual Environment and activate it using commands
```virtualenv *new_env_name*```
```cd /path/to/*new_env_name*/Scripts/```
```.\activate if using cmd or .\activate.ps1 if you are using powershell```

2. Clone this repository to your local machine:
```https://github.com/KLAU-S/Zummit-InfoLabs-Intern```

3. Install the required libraries: 
```pip install -r requirements.txt```

4. If you want to generate your own model Run the first part first, that will generate the model. if not skip running the first part and you can directly run realtime.py using command
```python realtime.py```

5. Enjoy !!!

## Authors

- **[Enayat Kareem, Brillia Benny, Swati Chaurasia, Avinash Kivande]** - *Initial work*

## License

No license, use it however you'd like, thankyou !

## Acknowledgments

- So many people to acknowledge, my family, my co-interns, my friends without which this project would not be completed, Special thanks to Brillia for the hard work and dedication, such a pleasure.

