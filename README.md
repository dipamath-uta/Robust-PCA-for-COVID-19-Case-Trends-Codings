📌 COVID-19 RPCA Project

Robust PCA comparison on global COVID-19 data using:

Convex PCP

Non-convex IRCUR RPCA (from a public robust-pca GitHub repo)

Weekly and daily matrices are decomposed into low-rank (trend) and sparse (anomaly) components to study case dynamics across continents and WHO regions.

🧩 Project Structure
covid-vax-project/
│
├── preprocessing/
│   └── build_weekly_matrices.py
│
├── robustpca/           # cloned/adapted GitHub repo
│   ├── ircur.py
│   ├── pcp.py
│   └── utils.py
│
├── run_pcp_covid.py
├── run_ircur_covid.py
├── plots/
│   └── *.png
└── data/
    └── *.csv

🌱 Requirements

Python 3.10–3.12

NumPy

SciPy

Pandas

Matplotlib

Install everything:

pip install -r requirements.txt

🚀 Running the Experiments
1. Build the weekly matrices
python preprocessing/build_weekly_matrices.py

2. Run convex RPCA (PCP)
python run_pcp_covid.py


Generates:

*_lowrank_pcp.csv

*_sparse_pcp.csv

plots in plots/

3. Run non-convex RPCA (IRCUR)
python run_ircur_covid.py


Produces:

*_lowrank_ircur.csv

*_sparse_ircur.csv

IRCUR plots in plots/

📊 Figures

Includes:

Daily vs Weekly low-rank comparisons

Daily vs Weekly sparse comparisons

PCP vs IRCUR comparisons

Weekly vaccination-vs-cases plots (context only)

All figures in the paper are reproducible from the scripts in this repository.

🔍 Non-Convex Method (IRCUR)

This project uses an IRCUR implementation adapted from the public robust-pca GitHub repository:
👉 https://github.com/sverdoot/robust-pca

IRCUR behaves as a non-convex RPCA algorithm that approximates low-rank structure using:

CUR-based submatrix sampling

iterative thresholding

truncated SVD on sampled rows/columns

Although capable of stronger rank selection, IRCUR exhibited instability on noisy epidemiological data, as documented in the report.

📚 Citation

If you use this code in academic work, please cite the original repository:

@sverdoot-robustpca
https://github.com/sverdoot/robust-pca

📬 Contact

Feel free to open an issue or email me:
Sadia Afrin Dipa
📧 dipacoumath@gmail.com
