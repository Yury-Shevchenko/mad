# User Manual

We have created the **Multi-Attribute Decision (MAD) builder** for researchers to help them to design a Mouselab task in a browser-based experiment. The MAD builder is available as either a template in the [lab.js](https://lab.js.org) or as a task in [Open Lab](https://open-lab.online). There are two ways to work with the MAD builder. One option is to open the template (JSON file) in the lab.js builder, which is free open-source software. Working in lab.js offers flexibility, as you can change not only the parameters, but also the design of your study. The second option is to open the MAD builder in Open Lab, an online platform for deployment of experiments. To modify the task, you have to edit its parameters (see *Table 1*). In the following, we will describe three different application scenarios to show how the parameters can be customized to your needs.

##Application scenarios

###Case 1: “Open information board with preset cue values”

In the first example, we consider the choice between two movies (“movie A” and “movie B”) based on the opinions of four experts who can either recommend a movie (+) or give no recommendation (-). Let's say we need 5 trials with feedback for 2 seconds after each trial telling participants whether they are correct or wrong.
We assume that you know exactly how cues should look like in each trial, so you don't require randomization, but wish to present the task in the order you defined from the start.

Figure 1: The movie task

![The movie task](https://raw.githubusercontent.com/Yury-Shevchenko/mad/master/images/Example%201.png)



###Scenario 2: “Closed Mouselab with randomization”

The second application scenario includes more randomization and applies the Mouselab paradigm in which users have to click on the boxes to open information. This time, it's about choosing between four different apartments based on five different cues. The cue values are generated independently with a probability of 40% to be a positive one. The feedback and the number of points are also displayed to participants. The participants click on the boxes to open the information and this information remains open until the end of the trial. We also make the information search costly and charge a certain number of points for each opened box. The options and cues are kept in the same order across trials.

Figure 2: Apartment-hunting task

![The apartment task](https://raw.githubusercontent.com/Yury-Shevchenko/mad/master/images/Example%202.png)

###Scenario 3: “The preferential choice with images”

The flexibility of the MAD Builder arises from the capability to upload your own images and use them as options, cues or cue values. In this case, we consider the task in which we ask people to choose between two food products. The first cue is the amount of calories (numbers), the second is the price ($), and the third cue is the country of origin (images of flags). Since it is a preferential choice, we will not estimate how correct the answer is and will not give participants any feedback.
In the lab.js experiment builder we need to upload images that will represent food products. Upload images on the screen component “MouseLab” and rename them to correspond to the values of the parameter *_ displayOptionsNames*.

Figure 3: Food preferences task

![The preference task](https://raw.githubusercontent.com/Yury-Shevchenko/mad/master/images/Example%203.png)


Table 1. The parameters

| Parameter name                       | Example                                         | Format                                                                                                                                | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
|--------------------------------------|-------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| _taskTitle                           | The multi-attribute decision task               | Text                                                                                                                                  | The title shown in the task                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| _numberOfTrials                      | 10                                              | Integer (min = 1)                                                                                                                     | The number of trials                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| _taskInstruction                     | Choose the bigger city                          | Text                                                                                                                                  | The instruction shown in the task                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| _optionsNames                        | Option1; Option2                                | Text, names are separated be semicolons.                                                                                              | The option names are for the researcher and not shown to a participant.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| _displayOptionsNames                 | London; Paris                                   | Text, names are separated be semicolons.                                                                                              | The display options names are shown to a participant.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| _cuesNames                           | Airport; Power Plant; University; Football team | Text, names are separated be semicolons.                                                                                              | The cues names displayed to the participant.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| _cuesValidity                        | 0.40; 0.30; 0.20; 0.10                          | Number, separated be semicolons.                                                                                                      | The validity values of the cues. The values should sum up to one and are used to calculate the correct option in each trial (by applying a weighted additive rule).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| _randomlyGenerateCues                | TRUE                                            | true / false                                                                                                                          | Whether to generate each cue independently with some probability. If true, then each cue value will be generated randomly and will be positive with the probability of the parameter *_probabilityOfPositiveCue*.  If false, then each cue value will be assigned a value from the parameter *_cueValuesForEachTrial*.                                                                                                                                                                                                                                                                                                                                                                                    |
| _probabilityOfPositiveCue            | 0.5                                             | Number between zero and one                                                                                                           | The probability of generating a positive cue. The parameter *_randomlyGenerateCues* should be true.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| _randomizeOrderOfTrials              | TRUE                                            | true / false                                                                                                                          | Whether or not to randomize the order of trials.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| _showFeedback                        | TRUE                                            | true / false                                                                                                                          | Whether or not to show feedback after each trial.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| _timeForFeedback                     | 1500                                            | Number of milliseconds (1000 is 1 sec)                                                                                                | How long to show feedback after the trial.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| _startingPoints                      | 1000                                            | Number                                                                                                                                | How many points participants have at the beginning of the task.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| _costOfLossTrial                     | 5                                               | Number                                                                                                                                | How many points participants lose in case of a wrong answer.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| _prizeOfWinTrial                     | 20                                              | Number                                                                                                                                | How many points participants win in case of a correct answer.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| _costOfOpenningOneCue                | 2                                               | Number                                                                                                                                | How many points participants pay to open one information box (in the closed Mouselab paradigm).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| _numberOfOptions                     | 2                                               | Number                                                                                                                                | The number of options. The number should be consistent with the parameters: *_optionsNames*, *_displayOptionsNames*, *_cueValuesForEachTrial* (if *_randomlyGenerateCues* is false).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| _numberOfCues                        | 4                                               | Number                                                                                                                                | The number of cues. The number should be consistent with the parameters: *_cuesNames*, *_cuesValidity*, *_cueValuesForEachTrial* (if *_randomlyGenerateCues* is false).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| _informationSearchParadigm           | closed                                          | open / closed                                                                                                                         | Whether to show all cues (open), or make them open on the mouse click (closed).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| _cuesBoxesBehavior                   | remainOpen                                      | remainOpen / closeAfterBoxIsLeft                                                                                                      | For closed Mouselab (*_informationSearchParadigm* is *closed*), whether to leave the boxes open after a click (remainOpen) or to hide the cue, when the mouse leaves the box (closeAfterBoxIsLeft).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| _numberOfOpenCuesFromStart        | 0                                               | Integer (min = 0)                                                                                                                     | For closed Mouselab (*_informationSearchParadigm* is *closed*), you can specify how many cues are visible from the beginning of the trial.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| _firstCuesToBeShownOnClick           | undefined                                       | Undefined or an array of first cues to show (separated by semicolons).                                                                | For closed Mouselab (*_informationSearchParadigm* is *closed*), you can specify which cue values to show on the first click. The cue values should be given as an array, which length is equal to the number of trials.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| _orderOfOptions                      | random                                          | random / ordered                                                                                                                      | Whether or not to randomize the presentation order of options specified in *_optionsNames*.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| _orderOfCues                         | ordered                                         | random / ordered                                                                                                                      | Whether or not to randomize the presentation order of cues.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| _decoupleOptionsAndDisplay | TRUE                                            | true / false                                                                                                                          | Whether or not to decouple display options names from options names. When true, the presentation order of displayed names is randomized independently from options.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| _showPoints                          | FALSE                                           | true / false                                                                                                                          | Whether or not to show participants the amount of collected points.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| _cueValuesForEachTrial               | 0;0;0;0;1;1;1;1 1;1;1;0;0;0;1;1 1;1;1;0;0;0;1;1 | Trials separated by a space or a new line. Cues are separated by semicolons. For convenience, the data can be copied from a csv file. | The cue values for each option and trial. The number of values should correspond to the number of trials, options and cues. The parameter *_randomlyGenerateCues* should be *false*.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| _imageNamePositive                   | thumbUp                                         | String, name of the image.                                                                                                            | In case if the parameter *_typeOfCues* is *name*, the positive cue value (bigger than 0) will be displayed with the image with given name. The image should uploaded to the screen component *MouseLab* in the lab.js builder, and the names should match.                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| _imageNameNegative                   | thumbDown                                       | String, name of the image.                                                                                                            | In case if the parameter *_typeOfCues* is *name*, the negative cue value (smaller or equal to 0) will be displayed with the image with given name.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| _showOptionsAsImages                 | TRUE                                            | true / false                                                                                                                          | Whether or not to show options as images. If true, display names will be used as images names.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| _showCuesAsImages                    | FALSE                                           | true / false                                                                                                                          | Whether or not to show cues as images. If true, cues names will be used as images names.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| _typeOfCues                          | binary                                          | binary / raw / image / name / any                                                                                                     | How to display cues: Binary:  *+* or *-*. If the cue is of *binary* type, the value bigger than zero is displayed as a plus sign, otherwise as a minus sign. Raw: the way how values are written in the parameter *_cueValuesForEachTrial*.  Image: as images for positive and negative values. The value bigger than zero is displayed as an image with the name from *_imageNamePositive*, otherwise as an image with the name from *_imageNameNegative*. Name: as images. The names of the images are in the parameter *_displayOptions*. Any: as images. The names of the images are in the parameter *_displayOptions*. If there is no image with the specified name, the raw value of cue is shown. |