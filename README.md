# Face-Mask-Classifier-Using-ML.NET
Face-Mask-Classifier-Using-ML.NET
<!-- wp:paragraph -->
<p><a rel="noreferrer noopener" href="https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet" target="_blank">ML.NET</a>&nbsp;is a cross-platform open-source machine learning framework that makes machine learning accessible to .NET developers.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>ML.NET Model Builder is an intuitive graphical Visual Studio extension to build, train, and deploy custom machine learning models.</p>
<!-- /wp:paragraph -->
<p> Add Machine Learning to a project</p>
<img src="./Screenshots/Screen0.png"/>

<p> Pick a Scenario</p>
<img src="./Screenshots/screen1.png"/>

<p>Data Folder</p>
<img src="./Screenshots/screen3.png"/>

<p>Train</p>
<img src="./Screenshots/screen2.png"/>

<p>Training progress</p>
<img src="./Screenshots/screen4.png"/>

<p>Training Result</p>

<p>Testing Images</p>
<img src="./Screenshots/1.jpg"/>
<img src="./Screenshots/screen5.png"/>

<img src="./Screenshots/2.jpg"/>
<img src="./Screenshots/Test2.png"/>


     public class ConsumeModel
    {
        // For more info on consuming ML.NET models, visit https://aka.ms/model-builder-consume
        // Method for consuming model in your app
        public static ModelOutput Predict(ModelInput input)
        {

            // Create new MLContext
            MLContext mlContext = new MLContext();

            // Load model & create prediction engine
            string modelPath = @"C:\Users\Hassan-Laptop\AppData\Local\Temp\MLVSTools\ConsoleApp2ML\ConsoleApp2ML.Model\MLModel.zip";
            ITransformer mlModel = mlContext.Model.Load(modelPath, out var modelInputSchema);
            var predEngine = mlContext.Model.CreatePredictionEngine<ModelInput, ModelOutput>(mlModel);

            // Use model to make prediction on input data
            ModelOutput result = predEngine.Predict(input);
            return result;
        }
    }
