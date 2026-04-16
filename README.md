# Motor_fault_predictions v1
 ✓ GPU detected and working!

Found 12/12 files

============================================================
BUILDING RMS DATASET
============================================================
Converting to RMS: 100% 12/12 [00:14<00:00,  1.11s/it]  ✓ Fullload_1_mu_rf3.csv: 1,000 cycles | samples/cycle=1000 | freq=50.000 Hz | source=zero_crossing_median
  ✓ Fullload_3_mu_Rf3.csv: 1,000 cycles | samples/cycle=1000 | freq=50.000 Hz | source=zero_crossing_median
  ✓ Fullload_5_mu_Rf3.csv: 1,000 cycles | samples/cycle=1000 | freq=50.000 Hz | source=zero_crossing_median
  ✓ Fullload_healthy.csv: 1,000 cycles | samples/cycle=1000 | freq=50.000 Hz | source=zero_crossing_median
  ✓ Halfload_1_mu_Rf3.csv: 1,000 cycles | samples/cycle=1000 | freq=50.000 Hz | source=zero_crossing_median
  ✓ Halfload_3_mu_Rf3.csv: 1,000 cycles | samples/cycle=1000 | freq=50.000 Hz | source=zero_crossing_median
  ✓ Halfload_5__rf3.csv: 1,000 cycles | samples/cycle=1000 | freq=50.000 Hz | source=zero_crossing_median
  ✓ Halfload_healthy.csv: 1,000 cycles | samples/cycle=1000 | freq=50.000 Hz | source=zero_crossing_median
  ✓ Noload_1_mu_Rf3.csv: 1,001 cycles | samples/cycle=999 | freq=50.050 Hz | source=zero_crossing_median
  ✓ Noload_3_mu_Rf3.csv: 1,001 cycles | samples/cycle=999 | freq=50.050 Hz | source=zero_crossing_median
  ✓ Noload_5_mu_Rf3.csv: 1,001 cycles | samples/cycle=999 | freq=50.050 Hz | source=zero_crossing_median
  ✓ Noload_healthy.csv: 1,001 cycles | samples/cycle=999 | freq=50.050 Hz | source=zero_crossing_median

✓ RMS dataset saved to 'processed_data/rms_cycle_dataset.csv'
✓ Total RMS rows: 12,004

============================================================
TRAINING ON RMS FEATURES
============================================================
Base cycles -> Train: 8,404 | Val: 2,399 | Test: 1,201
Expanded rows -> Train: 21,010 | Val: 5,997 | Test: 3,003

--- BINARY ---
  Classes in training: [0 1]
  Time: 0.7s | Val: 94.18% | Test: 93.71%

--- SEVERITY ---
  Classes in training: [0 1 2 3]
  Time: 1.8s | Val: 71.97% | Test: 70.33%

--- PHASE ---
  Classes in training: [0 1 2 3]
  Time: 2.0s | Val: 74.64% | Test: 72.39%

--- LOAD ---
  Classes in training: [0 1 2]
  Time: 0.8s | Val: 100.00% | Test: 100.00%

✓ Models saved to 'trained_models/'

============================================================
SUMMARY
============================================================

┌─────────────────┬────────────┬────────────┐
│ Task            │ Validation │ Test       │
├─────────────────┼────────────┼────────────┤
│ binary          │    94.18%  │    93.71%  │
│ severity        │    71.97%  │    70.33%  │
│ phase           │    74.64%  │    72.39%  │
│ load            │   100.00%  │   100.00%  │
└─────────────────┴────────────┴────────────┘

  
    

    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }


  
    
      
      I1_rms
      I2_rms
      I3_rms
      cycle_index
      source_file
      binary
      severity
      load
      sample_interval_s
      samples_per_cycle
      estimated_frequency_hz
      frequency_source
    
  
  
    
      0
      1.758211
      1.710003
      1.740000
      0
      Fullload_1_mu_rf3.csv
      1
      1
      2
      0.00002
      1000
      50.0
      zero_crossing_median
    
    
      1
      1.737056
      1.755879
      1.754459
      1
      Fullload_1_mu_rf3.csv
      1
      1
      2
      0.00002
      1000
      50.0
      zero_crossing_median
    
    
      2
      1.775897
      1.718151
      1.770994
      2
      Fullload_1_mu_rf3.csv
      1
      1
      2
      0.00002
      1000
      50.0
      zero_crossing_median
    
    
      3
      1.726389
      1.737007
      1.726535
      3
      Fullload_1_mu_rf3.csv
      1
      1
      2
      0.00002
      1000
      50.0
      zero_crossing_median
    
    
      4
      1.777734
      1.742260
      1.798517
      4
      Fullload_1_mu_rf3.csv
      1
      1
      2
      0.00002
      1000
      50.0
      zero_crossing_median
    
  


    

  
    

  
    
  
    

  
    .colab-df-container {
      display:flex;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    .colab-df-buttons div {
      margin-bottom: 4px;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  

    
      const buttonEl =
        document.querySelector('#df-4b3ac719-3422-4f0f-adb8-13732e0625cf button.colab-df-convert');
      buttonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';

      async function convertToInteractive(key) {
        const element = document.querySelector('#df-4b3ac719-3422-4f0f-adb8-13732e0625cf');
        const dataTable =
          await google.colab.kernel.invokeFunction('convertToInteractive',
                                                    [key], {});
        if (!dataTable) return;

        const docLinkHtml = 'Like what you see? Visit the ' +
          '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
          + ' to learn more about interactive tables.';
        element.innerHTML = '';
        dataTable['output_type'] = 'display_data';
        await google.colab.output.renderOutput(dataTable, element);
        const docLink = document.createElement('div');
        docLink.innerHTML = docLinkHtml;
        element.appendChild(docLink);
      }
    
  


    
  
