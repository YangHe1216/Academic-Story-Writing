# Example — Selected LaTeX Paragraph Only

> Synthetic illustration. Numeric values are invented for this example.

## Selected passage

```latex
We may potentially observe some performance improvements for our method on dataset~\texttt{D},
where the score changes from 71.0 to 73.0, although more datasets would be needed to
make meaningful claims about this particular comparison. See Table~\ref{tab:ablation}.
```

## Academic Story Writing local edit

```latex
On dataset~\texttt{D}, our method improves the measured score from 71.0 to 73.0
under the evaluated protocol (Table~\ref{tab:ablation}).
```

Scope: only the selected paragraph changed. The dataset, numbers, and LaTeX reference remain; no universal generalization or cross-seed stability is inferred. If the actual source does **not** support the comparison (e.g., mismatched baselines), identify the concrete issue and adjust accordingly.
