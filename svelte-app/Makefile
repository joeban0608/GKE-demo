# 定義專案路徑
gcp_artifact_registry_path = asia-east1-docker.pkg.dev/seo-manager-429705/test-joe-svelte-app/svelte-app
workspace_path = /Users/hongbangzhou/sign-projects/GKE-demo
app_path = svelte-app
gke_path = kustomize-GKE

# 使用變數在 docker build 中
app-dev-build:
	cd $(workspace_path) && \
	docker build -t ${gcp_artifact_registry_path}:dev --platform linux/amd64 -f $(workspace_path)/$(app_path)/Dockerfile $(workspace_path)/$(app_path)

app-dev-push:
		cd $(workspace_path) && \
		docker push ${gcp_artifact_registry_path}:dev

k8s-app-dev-apply:
		kubectl apply -k $(workspace_path)/$(gke_path)/overlays/dev
		

app-prod-build:
	cd $(workspace_path) && \
	docker build -t ${gcp_artifact_registry_path}:prod --platform linux/amd64 -f $(workspace_path)/$(app_path)/Dockerfile $(workspace_path)/$(app_path)

app-prod-push:
		cd $(workspace_path) && \
		docker push ${gcp_artifact_registry_path}:prod

k8s-app-prod-apply:
		kubectl apply -k $(workspace_path)/$(gke_path)/overlays/prod