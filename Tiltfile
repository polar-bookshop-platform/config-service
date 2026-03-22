# Build
custom_build(
    # Name of the container image
    ref = 'config-service',
    # Command to build the container image
    # 윈도우 환경 $EXPECTED_REF -> %EXPECTED_REF%, gradlew 앞의 ./를 제거
    # e.g. command = './gradlew bootBuildImage --imageName $EXPECTED_REF%'
    command = 'gradlew bootBuildImage --imageName %EXPECTED_REF%',
    # Files to watch that trigger a new build
    deps = ['build.gradle', 'src']
)

# Deploy
k8s_yaml(['k8s/deployment.yaml', 'k8s/service.yaml'])

# Manage
k8s_resource('config-service', port_forwards=['8888'])
