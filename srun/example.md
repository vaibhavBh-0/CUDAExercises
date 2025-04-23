# Run interactive session using srun via login nodes
> srun --account=bbvi-delta-gpu --partition=gpuA40x4-interactive --nodes=1 --gpus-per-node=1 --mem=10g --tasks=1 --pty bash
