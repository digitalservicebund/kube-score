# run-kube-score GHA

## About

This GHA installs and runs [kube-score](https://github.com/zegl/kube-score) with Kustomize. CI will fail if a critical issue is found. Learn more about [kube-score's checks here](https://github.com/zegl/kube-score?tab=readme-ov-file#checks).

## Example

Add this job to your infra repository's CI:

```yaml
kube-score:
  strategy:
    matrix:
      # Add relevant environments (staging, production, etc.)
      stage:
        - staging
  runs-on: ubuntu-latest
  steps:
    - uses: actions/checkout@v4
    - name: Run kube-score
      uses: digitalservicebund/kube-score@HASH_PLACEHOLDER
      with:
        manifests_path: manifests/overlays/${{ matrix.stage }}
```

## Updating this action

After merging a dependabot PR or pushing changes, you need to [cut a new release](https://docs.github.com/en/repositories/releasing-projects-on-github/managing-releases-in-a-repository).

## Contributing

🇬🇧
Everyone is welcome to contribute the development of the _kotlin-application-template_. You can contribute by opening pull request,
providing documentation or answering questions or giving feedback. Please always follow the guidelines and our
[Code of Conduct](CODE_OF_CONDUCT.md).

🇩🇪
Jede:r ist herzlich eingeladen, die Entwicklung der _kotlin-application-template_ mitzugestalten. Du kannst einen Beitrag leisten,
indem du Pull-Requests eröffnest, die Dokumentation erweiterst, Fragen beantwortest oder Feedback gibst.
Bitte befolge immer die Richtlinien und unseren [Verhaltenskodex](CODE_OF_CONDUCT_DE.md).

### Contributing code

🇬🇧
Open a pull request with your changes and it will be reviewed by someone from the team. When you submit a pull request,
you declare that you have the right to license your contribution to the DigitalService and the community.
By submitting the patch, you agree that your contributions are licensed under the MIT license.

Please make sure that your changes have been tested befor submitting a pull request.

🇩🇪
Nach dem Erstellen eines Pull Requests wird dieser von einer Person aus dem Team überprüft. Wenn du einen Pull Request
einreichst, erklärst du dich damit einverstanden, deinen Beitrag an den DigitalService und die Community zu
lizenzieren. Durch das Einreichen des Patches erklärst du dich damit einverstanden, dass deine Beiträge unter der
MIT-Lizenz lizenziert sind.

Bitte stelle sicher, dass deine Änderungen getestet wurden, bevor du einen Pull Request sendest.
