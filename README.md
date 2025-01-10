# longvu_ckpt_fixes
Fixes that may help with saving &amp; resuming training with LongVU's codebase under deepspeed

To use deepspeed instead of FSDP (see [this discussion on LongVU's repo](https://github.com/Vision-CAIR/LongVU/issues/21)), remove all FSDP-related arguments that are passed to `train.py` and instead use `--deepspeed $path_to_deepspeed_config`. A suggested deepspeed config `.json` can be found in this repo. Under the assumption that LongVU "inherits" some of the issues related to resuming training from VideoLlaVA (see their github issues for related discussions), I've changed some `.py` files which can also be found here (diff-ing with the original can show what changes were made).

**Note**: these fixes worked for me but I take no responsibility whatsoever whether they'll work for your environment as well.
