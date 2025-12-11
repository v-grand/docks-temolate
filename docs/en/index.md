# Welcome to v-grand Platform Documentation

Welcome to the comprehensive documentation for the **v-grand ecosystem**. Here you will find information about the various platform components, their purpose, and how to use them.

## 📚 Platform Overview

For a general understanding of the platform's structure and core services, please visit the page:

[**Platform Overview**](platform-overview.md)

## 🚀 Quick Start

### For New Projects

1.  **Clone the template:**
    ```bash
    git clone https://github.com/v-grand/infra-template.git my-new-project
    cd my-new-project
    ```

2.  **Configure your environment:**
    ```bash
    cp terraform.tfvars.example terraform.tfvars
    # Edit terraform.tfvars with your settings
    ```

3.  **Deploy:**
    ```bash
    terraform init
    terraform plan
    terraform apply
    ```

### For Existing Projects

Choose the appropriate repository based on your needs:

-   **AWS Deployment** → [infra-aws](aws.md)
-   **GCP Deployment** → [infra-gcp](gcp/index.md)
-   **Kubernetes** → [infra-k8s.md](infra-k8s.md)
-   **Monitoring** → [infra-monitoring.md](infra-monitoring.md)

## 🔗 External Resources

-   [Terraform Documentation](https://www.terraform.io/docs)
-   [GitHub Actions Documentation](https://docs.github.com/en/actions)
-   [AWS Well-Architected Framework](https://aws.amazon.com/architecture/well-architected/)
-   [Google Cloud Architecture Center](https://cloud.google.com/architecture)

## 🤝 Contributing

We welcome contributions! Please see the individual repository guidelines for contribution instructions.

## 📄 License

All repositories are licensed under the MIT License unless otherwise specified.
