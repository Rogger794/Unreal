# Unreal

1. Crear una cuenta de  [Unreal](https://accounts.unrealengine.com/login?lang=en_US)

2. Asociar su cuenta de Github a su cuenta de Unreal, editando tu cuenta dentro de [personal](https://www.unrealengine.com/dashboard) en [edit profile](https://www.unrealengine.com/dashboard/settings).

3. Clone el motor gráfico, una vez sincronizada su cuenta.

  ```
  git clone https://github.com/EpicGames/UnrealEngine
  ```

4.  Instalamos paquetes necesarios:

  ```
  sudo apt-get install build-essential mono-xbuild mono-dmcs libmono-corlib4.5-cil libmono-system-data-datasetextensions4.0-cil libmono-system-web-extensions4.0-cil libmono-system-management4.0-cil libmono-system-xml-linq4.0-cil cmake dos2unix clang-3.5 xdg-user-dirs git
  ```

5. Creamos enlaces simbólicos por si el clang no los crea automáticamente

  ```
  sudo ln -s /usr/bin/clang-3.5 /usr/bin/clang
  sudo ln -s /usr/bin/clang++-3.5 /usr/bin/clang++
  ```

6. Ejecutamos los scripts sin usar sudo, ni estar como superusuario.

  ```
  cd UnrealEngine
  ./Setup.sh
  ./GenerateProjectFiles.sh
  ```

7. Construimos el editor de Unreal Engine 4

  ```
  make SlateViewer
  make UE4Editor ARGS=-clean
  make ShaderCompileWorker UnrealLightmass UnrealPak CrashReportClient UE4Editor
  ```

8. Ejecutar Unreal Engine 4

  ```
  cd Engine/Binaries/Linux && ./UE4Editor
  ```
