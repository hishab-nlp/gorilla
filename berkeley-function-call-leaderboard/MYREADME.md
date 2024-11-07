
## Adding New Functionary(VLLM) Model
- Add the model handler in script `bfcl/model_handler/handler_map.py`

    Under `api_inference_handler_map` add the model name and it's corresponding handler.
    Example: `"meetkai/functionary-medium-v3.2-FC": FunctionaryHandler`

- Update `UNDERSCORE_TO_DOT` model list according to the new model in `bfcl/model_handler/constant.py`

example: `"meetkai/functionary-medium-v3.2-FC"`

- Update `model_metadata` in `bfcl/eval_checker/model_metadata.py`

    Update `MODEL_METADATA_MAPPING` add like below example:

    ```JSON
    "meetkai/functionary-medium-v3.2-FC": [
        "Functionary-Medium-v3.2 (FC)",
        "https://huggingface.co/meetkai/functionary-medium-v3.2",
        "MeetKai",
        "MIT",
    ]

    ```

Everything is done. Now you can generate result by below commands

`bfcl generate --model meetkai/functionary-medium-v3.2-FC --test-category simple --num-threads 1`