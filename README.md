PROJECT COLOR HELMET DETECTION
The object detection model identifies helemt and determine what is the color of it. 
Based on what color is absent from a current video or network stream the model generates out put and stores in db and pictures in the file system.

steps to execute the project.

1. Clone this repository into the edge box.
2. In a RDS or Local database create a schema and use eSentinel_new.sql to create the necessary tables.
3. Need to create a pipeline_id as per pipeline master table manually. Make sure to link the table with camera, model and pipeline_class_map to get the necessary data to create an alert.
4. Get and Set the pipeline id in run.sh file.
5. If there is an requirement of ROI insert into ROI or leave as a blank string. determine the ROI by zoning_tool.py
6. The parameter export TIME_ZONE='Asia/Singapore' sets and records the alerts as per specific timezone. by defult it is set to singapore time.
7. The parameter export NON_COMPLIANCE_HELMET_COLOR='WHITE' # 'WHITE', 'YELLOW', 'RED' , 'BLUE' , 'GREEN' , 'GRAY' is to specify, based on what it should generate alerts.
   for example any one color from this mention above is not present in a current frame will generate an alert.
6. execute the run file through sh run.sh to execute the project.
