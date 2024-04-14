# LegalEASE 

### Contributors 
Jordan Fan, John Gibbons, Elias Tavarez

## About / Synopsis 

Abstractive summarization of US congressional bills utilizing 2-stage summarization approach. 

## Data Sources
* US Congressional data - https://huggingface.co/datasets/hheiden/us-congress-117-bills
* BillSum - https://huggingface.co/datasets/billsum

## Folders/Notebooks

### Data Processing
* data_processing/data_processing_extractive.ipynb -
* data_processing/BILLSUM_BART_1st_stage_abstractive_summarization.ipynb - fine-tune BART on BillSum dataset to generate first stage abstractive summaries.
* data_processing/billsum_to_congress_117_summarization_middle_50_percent.ipynb - Applies fine-tuned BART model on BillSum dataset to generate first stage abstractive summaries on US congressional bills within the 25-75th percentile of word counts.
* data_processing/billsum_to_congress_117_summarization_outer_50_percent.ipynb - Applies fine-tuned BART model on BillSum dataset to generate first stage abstractive summaries on US congressional bills between the 0-25th and 75-97.5th percentile of word counts. Combines the first stage abstractive summaries together.

### BART
* BART/BART.ipynb - fine-tune BART model using original bill text 
* BART/BART_peft.ipynb - fine-tune BART model using original bill text and utilizing peft framework 
* BART/BART_tf_extractive.ipynb - fine-tune BART model using term-frequency extractive summary text 
* BART/BART_bertsum_extractive.ipynb - fine-tune BART model using BERTSum extractive summary text 
* BART/BART_billsum_abstractive.ipynb - fine-tune BART model using abstractive summary text 
* BART/bart_test_evaluation.ipynb - calculate ROUGE, BLEURT, Entailment, and Readability metrics on each BART model against the test set

### MISC
* MISC/categorical_evaluation.ipynb - calculate ROUGE, BLEURT, Entailment, and Readability metrics for the grouped categories based on number of bills

### PEGASUS
* PEGASUS/manual_evaluation.ipynb - generate summaries for specific bills using pegasus
* PEGASUS/model_evaluation.ipynb - calculate ROUGE and BLEURT metrics on each PEGASUS model against the test set
* PEGASUS/model_training.ipynb - fine-tune PEGASUS model using original bill text
* PEGASUS/readability_entail_evaluation - calculate Entailment and Readability metrics on each PEGASUS model against the test set

### T5
* T5/summary_manual_eval.ipynb - generate summaries for specific bills using T5
* T5/T5_test_eval.ipynb - calculate ROUGE and BLEURT metrics on each T5 model against the test set
* T5/T5.ipynb - fine-tune T5 model using original bill text
* T5/T5_peft.ipynb - fine-tune T5 model using original bill text and utilizing peft framework 

