# AI-fraud-detection-system
Pick the dataset/model direction (we're close — lock that in first, since everything else wraps around it).
Baseline model — nothing fancy yet, just something that trains and outputs predictions. This unblocks everything downstream.
Wrap it as a service — small FastAPI app with a /predict endpoint, running locally.
Containerize it — Docker image, runs locally via docker run.
Get it running on local Kubernetes (kind/minikube in WSL2) — this is your "infra skeleton" proof that the deployment story works before AWS costs anything.
Bare-bones website — a page that calls your local API and shows a result. Ugly is fine; the goal is proving the wiring end-to-end.
→ At this point you have a complete, working, ugly version of the whole system. Everything after this is "make each piece better," in whatever order excites you most:

Level up the model (this is where the advanced ML work — feature engineering, ensembling, GNNs, etc. — happens, now that you have a place to plug it in).
Move infra to AWS via Terraform (ECR, EKS, S3, IAM) and wire up CI/CD (GitHub Actions).
Add observability — MLflow for experiments, Prometheus/Grafana for serving metrics, drift monitoring.
Polish the website — real design, architecture diagrams, live-demo styling, write-up of decisions.
