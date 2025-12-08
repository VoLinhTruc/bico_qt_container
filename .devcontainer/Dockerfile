FROM ghcr.io/volinhtruc/bico_ubuntu:22.04_0.0.0

USER root

RUN apt-get update

RUN apt install -y \
        qt6-base-dev \
        qt6-base-private-dev \
        qt6-declarative-dev \
        qt6-declarative-private-dev \
        qt6-tools-dev \
        qt6-tools-private-dev \
        qt6-scxml-dev \
        qt6-documentation-tools \
        libqt6core5compat6-dev \
        qt6-tools-dev-tools \
        qt6-l10n-tools \
        qt6-shader-baker \
        libqt6shadertools6-dev \
        qt6-quick3d-dev \
        qt6-quick3d-dev-tools \
        libqt6svg6-dev \
        libqt6quicktimeline6-dev \
        libqt6serialport6-dev

RUN apt install -y \
        qt6-wayland \
        libqt6waylandclient6 \
        libwayland-dev \

RUN apt install -y \
        qml6-module-qt3d-animation \
        qml6-module-qt3d-core \
        qml6-module-qt3d-extras \
        qml6-module-qt3d-input \
        qml6-module-qt3d-logic \
        qml6-module-qt3d-render \
        qml6-module-qt5compat-graphicaleffects \
        qml6-module-qtcharts \
        qml6-module-qtcore \
        qml6-module-qtdatavisualization \
        qml6-module-qt-labs-animation \
        qml6-module-qt-labs-folderlistmodel \
        qml6-module-qt-labs-lottieqt \
        qml6-module-qt-labs-platform \
        qml6-module-qt-labs-qmlmodels \
        qml6-module-qt-labs-settings \
        qml6-module-qt-labs-sharedimage \
        qml6-module-qt-labs-wavefrontmesh \
        qml6-module-qtmultimedia \
        qml6-module-qtpositioning \
        qml6-module-qtqml-models \
        qml6-module-qtqml \
        qml6-module-qtqml-statemachine \
        qml6-module-qtqml-workerscript \
        qml6-module-qtqml-xmllistmodel \
        qml6-module-qtquick-controls \
        qml6-module-qtquick-dialogs \
        qml6-module-qtquick-layouts \
        qml6-module-qtquick-localstorage \
        qml6-module-qtquick-nativestyle \
        qml6-module-qtquick-particles \
        qml6-module-qtquick-pdf \
        qml6-module-qtquick \
        qml6-module-qtquick-scene2d \
        qml6-module-qtquick-scene3d \
        qml6-module-qtquick-shapes \
        qml6-module-qtquick-templates \
        qml6-module-qtquick-timeline \
        qml6-module-qtquick-tooling \
        qml6-module-qtquick-virtualkeyboard \
        qml6-module-qtquick-window \
        qml6-module-qtremoteobjects \
        qml6-module-qtscxml \
        qml6-module-qtsensors \
        qml6-module-qttest \
        qml6-module-qtwayland-client-texturesharing \
        qml6-module-qtwayland-compositor \
        qml6-module-qtwebchannel \
        qml6-module-qtwebengine-controlsdelegates \
        qml6-module-qtwebengine \
        qml6-module-qtwebsockets \
        qml6-module-qtwebview \
        qml6-module-quick3d-assetutils \
        qml6-module-quick3d-effects \
        qml6-module-quick3d-helpers \
        qml6-module-quick3d-particles3d \
        qml6-module-quick3d


RUN apt install -y \
        clang-15 \
        clangd-15 \
        libclang-15-dev

RUN apt install -y \
        libgl1-mesa-dev \
        libvulkan-dev \
        libxcb-xinput-dev \
        libxcb-xinerama0-dev \
        libxkbcommon-dev \
        libxkbcommon-x11-dev \
        libxcb-image0 \
        libxcb-keysyms1 \
        libxcb-render-util0 \
        libxcb-xkb1 \
        libxcb-randr0 \
        libxcb-icccm4
RUN apt-get -y install qtcreator

#  Fix issue with missing libxcb-cursor0 dependency for PyQt
# qt.qpa.plugin: From 6.5.0, xcb-cursor0 or libxcb-cursor0 is needed to load the Qt xcb platform plugin.
# qt.qpa.plugin: Could not load the Qt platform plugin "xcb" in "" even though it was found.
RUN apt-get install -y \
        libxcb-cursor0

# RUN apt-get -y install qtbase5-dev qtdeclarative5-dev libqt5svg5-dev qt5-qmake qtbase5-dev-tools
# RUN apt-get -y install qt6-base-dev qt6-base-dev-tools qt6-tools-dev qt6-tools-dev-tools qt6-declarative-dev libqt6svg6-dev
# RUN apt-get -y install qtcreator

# # Clean up apt-get cache to reduce image size
# RUN apt-get clean && \
#     rm -rf /var/lib/apt/lists/*

USER $USERNAME

# # Qt5
# RUN pip install PySide2
# Qt6
RUN pip install PySide6==6.9.1

WORKDIR /tmp
RUN curl -L -o qt-online-installer-linux-x64-online.run https://download.qt.io/official_releases/online_installers/qt-online-installer-linux-x64-online.run

CMD ["bash"]