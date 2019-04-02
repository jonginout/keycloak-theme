# keycloak-theme
### keycloak basic theme (docker image)
```
keycloak:
  extraInitContainers: |
    - name: theme-provider
      image: myuser/mytheme:1
      imagePullPolicy: IfNotPresent
      command:
        - sh
      args:
        - -c
        - |
          echo "Copying theme..."
          cp -R /my_theme/* /theme
      volumeMounts:
        - name: theme
          mountPath: /theme

  extraVolumeMounts: |
    - name: theme
      mountPath: /opt/jboss/keycloak/themes/mytheme

  extraVolumes: |
    - name: theme
      emptyDir: {}
 ```
 
 
 
![img](https://cdn-images-1.medium.com/max/1400/0*49oKObDvfQyfw5WH.)
