# Pest Detection Analysis - Setup Guide


## 📁 Dataset Structure

```
archive (2)/
├── train/
│   ├── ants/
│   ├── bees/
│   ├── beetle/
│   ├── catterpillar/
│   ├── earthworms/
│   ├── earwig/
│   ├── grasshopper/
│   ├── moth/
│   ├── slug/
│   ├── snail/
│   ├── wasp/
│   └── weevil/
└── test/
    ├── ants/
    ├── bees/
    ├── beetle/
    └── ... (same structure)
```

**Total Classes:** 12 pest categories

## 🚀 How to Run

### Step 1: Install Required Libraries
Open a terminal in VS Code and run:
```powershell
pip install tensorflow numpy pandas matplotlib seaborn pillow opencv-python scikit-learn
```

### Step 2: Run the Notebook
1. Open `pest_detection_analysis.ipynb`
2. Run cells sequentially (Shift + Enter)
3. The notebook will automatically:
   - Load your pest images from the train/test folders
   - Count images in each class
   - Display sample images
   - Train 3 different models (LeNet-5, VGG16, MobileNetV2)
   - Compare their performance

## 📊 What's Updated

### ✅ Changes Made:
1. **Dataset Path**: Updated to your actual path `C:\Users\Soumil\Downloads\archive (2)`
2. **Number of Classes**: Automatically detects 12 pest classes
3. **Data Loading**: Uses `ImageDataGenerator.flow_from_directory()` to load images
4. **Image Visualization**: Added cell to display sample pest images
5. **Training**: All models now train on your real pest dataset
6. **Validation**: Uses your test folder for validation

### 🎯 Key Features:
- **Automatic class detection** from folder structure
- **Real-time image counting** for train/test sets
- **Data augmentation** for better model performance
- **Proper train/test split** using your folder structure

## 📈 Expected Output

When you run the notebook, you'll see:

### Cell Output Example:
```
✓ Training directory found: C:\Users\Soumil\Downloads\archive (2)\train
✓ Number of pest classes: 12
✓ Pest categories: ants, bees, beetle, catterpillar, earthworms, earwig, grasshopper, moth, slug, snail, wasp, weevil

📊 TRAINING SET:
   Total images: XXXX
   - ants: XX images
   - bees: XX images
   - beetle: XX images
   ... (and so on)

📊 TESTING SET:
   Total images: XXXX
   - ants: XX images
   - bees: XX images
   ... (and so on)
```

## 🎨 Visualizations Included

1. **Sample pest images** from training set
2. **Training/validation accuracy curves** for all 3 models
3. **Energy consumption comparison**
4. **Model complexity vs accuracy trade-off**
5. **Comprehensive comparison dashboard**

## ⚙️ Model Configurations

### Modified LeNet-5
- Image size: 128x128
- Most energy-efficient (123.2J per cycle)
- Best for edge deployment

### VGG16
- Image size: 128x128
- Highest accuracy
- More computational cost (181.2J per cycle)

### MobileNetV2
- Image size: 128x128
- Mobile-optimized
- Good balance (200.1J per cycle)

## 🔧 Configuration Parameters

You can adjust these in the notebook:
```python
IMG_SIZE = 128        # Image resolution
BATCH_SIZE = 32       # Batch size for training
EPOCHS = 50           # Number of training epochs
```

## 📝 Notes

- The notebook uses **data augmentation** (rotation, flipping, zoom) to improve model robustness
- Training time depends on:
  - Number of images in your dataset
  - GPU availability (much faster with GPU)
  - Number of epochs
- Models are saved in `saved_models/` folder after training

## 🎯 Next Steps

1. Run the notebook cells sequentially
2. Wait for models to train (this may take 20-60 minutes depending on hardware)
3. Review the comparison results
4. Use the saved models for deployment

## ⚠️ Troubleshooting

**If you get "directory not found" error:**
- Check that the path `C:\Users\Soumil\Downloads\archive (2)` exists
- Make sure train and test folders are inside it
- Verify folder names match exactly (case-sensitive)

**If training is too slow:**
- Reduce `EPOCHS` to 20-30
- Reduce `IMG_SIZE` to 64 or 96
- Reduce `BATCH_SIZE` to 16

**If you run out of memory:**
- Reduce `BATCH_SIZE` to 16 or 8
- Close other applications
- Restart the kernel

---

🎉 **You're all set!** Start running the cells and let the models train on your real pest dataset!
