python package인 geopandas를 설치하려니 아래와 같은 에러 로그가 떴다.

```
Collecting fiona
  Using cached Fiona-1.8.18.tar.gz (1.3 MB)
    ERROR: Command errored out with exit status 1:
     command: 'c:\users\{username}\appdata\local\programs\python\python37\python.exe' -c 'import sys, setuptools, tokenize; sys.argv[0] = '"'"'C:\\Users\\{username}\\AppData\\Local\\Temp\\pip-install-yrrv41xd\\fiona\\setup.py'"'"'; __file__='"'"'C:\\Users\\{username}\\AppData\\Local\\Temp\\pip-install-yrrv41xd\\fiona\\setup.py'"'"';f=getattr(tokenize, '"'"'open'"'"', open)(__file__);code=f.read().replace('"'"'\r\n'"'"', '"'"'\n'"'"');f.close();exec(compile(code, __file__, '"'"'exec'"'"'))' egg_info --egg-base 'C:\Users\{username}\AppData\Local\Temp\pip-pip-egg-info-y2__lb18'
         cwd: C:\Users\{username}\AppData\Local\Temp\pip-install-yrrv41xd\fiona\
    Complete output (1 lines):
    A GDAL API version must be specified. Provide a path to gdal-config using a GDAL_CONFIG environment variable or use a GDAL_VERSION environment variable.
    ----------------------------------------
ERROR: Command errored out with exit status 1: python setup.py egg_info Check the logs for full command output.
```


```$dir *.whl```커맨드로 필요한 whl파일이 다 다운받아져 있는지 확인해보자.

```
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----     2020-11-19   오후 2:45         527956 Fiona-1.8.17-cp37-cp37m-win_amd64.whl
-a----     2020-11-19   오후 2:38       29297237 GDAL-3.1.4-cp37-cp37m-win_amd64.whl
```



geopandas 패키지를 설치하기 전에 필요한 패키지를 반드시 이 순서에 맞춰 설치해야한다.

pyproj, shapely, GDAL, Fiona, geopandas

Fiona와 GDAL패키지를 설치할 때에는 반드시 버전 명시를 해주어야 한다. 하지 않으면 아래와 같이 에러가 뜬다. 아래 로드는 버전 명시하지 않고 설치 후 다시 버전 명시해 설치 성공한 로그이다.

```
PS C:\Users\{username}\1110_server (2)> pip install GDAL
Collecting GDAL
  Using cached GDAL-3.2.0.tar.gz (602 kB)
Building wheels for collected packages: GDAL
  Building wheel for GDAL (setup.py) ... error
  ERROR: Command errored out with exit status 1:
   command: 'c:\users\{username}\appdata\local\programs\python\python37\python.exe' -u -c 'import sys, setuptools, tokenize; sys.argv[0] = '"'"'C:\\Users\\{username}\\AppData\\Local\\Temp\\pip-install-_i2yl6qm\\gdal\\setup.py'"'"'; __file__='"'"'C:\\Users\\{username}\\AppData\\Local\\Temp\\pip-install-_i2yl6qm\\gdal\\setup.py'"'"';f=getattr(tokenize, '"'"'open'"'"', open)(__file__);code=f.read().replace('"'"'\r\n'"'"', '"'"'\n'"'"');f.close();exec(compile(code, __file__, '"'"'exec'"'"'))' 
bdist_wheel -d 'C:\Users\{username}\AppData\Local\Temp\pip-wheel-za9d8_4q'
       cwd: C:\Users\{username}\AppData\Local\Temp\pip-install-_i2yl6qm\gdal\
  Complete output (54 lines):
  running bdist_wheel
  running build
  running build_py
  creating build
  creating build\lib.win-amd64-3.7
  creating build\lib.win-amd64-3.7\osgeo
  copying osgeo\gdal.py -> build\lib.win-amd64-3.7\osgeo
  copying osgeo\gdalconst.py -> build\lib.win-amd64-3.7\osgeo
  copying osgeo\gdalnumeric.py -> build\lib.win-amd64-3.7\osgeo
  copying osgeo\gdal_array.py -> build\lib.win-amd64-3.7\osgeo
  copying osgeo\gnm.py -> build\lib.win-amd64-3.7\osgeo
  copying osgeo\ogr.py -> build\lib.win-amd64-3.7\osgeo
  copying osgeo\osr.py -> build\lib.win-amd64-3.7\osgeo
  copying osgeo\__init__.py -> build\lib.win-amd64-3.7\osgeo
  creating build\lib.win-amd64-3.7\osgeo\utils
  copying osgeo\utils\epsg_tr.py -> build\lib.win-amd64-3.7\osgeo\utils
  copying osgeo\utils\esri2wkt.py -> build\lib.win-amd64-3.7\osgeo\utils
  copying osgeo\utils\gcps2vec.py -> build\lib.win-amd64-3.7\osgeo\utils
  copying osgeo\utils\gcps2wld.py -> build\lib.win-amd64-3.7\osgeo\utils
  copying osgeo\utils\gdal2xyz.py -> build\lib.win-amd64-3.7\osgeo\utils
  copying osgeo\utils\gdalchksum.py -> build\lib.win-amd64-3.7\osgeo\utils
  copying osgeo\utils\gdalcompare.py -> build\lib.win-amd64-3.7\osgeo\utils
  copying osgeo\utils\gdalident.py -> build\lib.win-amd64-3.7\osgeo\utils
  copying osgeo\utils\gdalimport.py -> build\lib.win-amd64-3.7\osgeo\utils
  copying osgeo\utils\gdalmove.py -> build\lib.win-amd64-3.7\osgeo\utils
  copying osgeo\utils\gdal_auth.py -> build\lib.win-amd64-3.7\osgeo\utils
  copying osgeo\utils\gdal_calc.py -> build\lib.win-amd64-3.7\osgeo\utils
  copying osgeo\utils\gdal_edit.py -> build\lib.win-amd64-3.7\osgeo\utils
  copying osgeo\utils\gdal_fillnodata.py -> build\lib.win-amd64-3.7\osgeo\utils
  copying osgeo\utils\gdal_merge.py -> build\lib.win-amd64-3.7\osgeo\utils
  copying osgeo\utils\gdal_pansharpen.py -> build\lib.win-amd64-3.7\osgeo\utils
  copying osgeo\utils\gdal_polygonize.py -> build\lib.win-amd64-3.7\osgeo\utils
  copying osgeo\utils\gdal_proximity.py -> build\lib.win-amd64-3.7\osgeo\utils
  copying osgeo\utils\gdal_retile.py -> build\lib.win-amd64-3.7\osgeo\utils
  copying osgeo\utils\gdal_sieve.py -> build\lib.win-amd64-3.7\osgeo\utils
  copying osgeo\utils\mkgraticule.py -> build\lib.win-amd64-3.7\osgeo\utils
  copying osgeo\utils\ogrmerge.py -> build\lib.win-amd64-3.7\osgeo\utils
  copying osgeo\utils\pct2rgb.py -> build\lib.win-amd64-3.7\osgeo\utils
  copying osgeo\utils\rgb2pct.py -> build\lib.win-amd64-3.7\osgeo\utils
  copying osgeo\utils\__init__.py -> build\lib.win-amd64-3.7\osgeo\utils
  c:\users\{username}\appdata\local\programs\python\python37\lib\site-packages\setuptools\lib2to3_ex.py:44: SetuptoolsDeprecationWarning: 2to3 support is deprecated. If the project still requires Python 2 support, please migrate to a single-codebase solution or employ an independent conversion process.
    SetuptoolsDeprecationWarning)
  Fixing build\lib.win-amd64-3.7\osgeo\gdal.py build\lib.win-amd64-3.7\osgeo\gdalconst.py build\lib.win-amd64-3.7\osgeo\gdalnumeric.py build\lib.win-amd64-3.7\osgeo\gdal_array.py build\lib.win-amd64-3.7\osgeo\gnm.py build\lib.win-amd64-3.7\osgeo\ogr.py build\lib.win-amd64-3.7\osgeo\osr.py build\lib.win-amd64-3.7\osgeo\__init__.py build\lib.win-amd64-3.7\osgeo\utils\epsg_tr.py build\lib.win-amd64-3.7\osgeo\utils\esri2wkt.py build\lib.win-amd64-3.7\osgeo\utils\gcps2vec.py build\lib.win-amd64-3.7\osgeo\utils\gcps2wld.py build\lib.win-amd64-3.7\osgeo\utils\gdal2xyz.py build\lib.win-amd64-3.7\osgeo\utils\gdalchksum.py build\lib.win-amd64-3.7\osgeo\utils\gdalcompare.py build\lib.win-amd64-3.7\osgeo\utils\gdalident.py build\lib.win-amd64-3.7\osgeo\utils\gdalimport.py build\lib.win-amd64-3.7\osgeo\utils\gdalmove.py build\lib.win-amd64-3.7\osgeo\utils\gdal_auth.py build\lib.win-amd64-3.7\osgeo\utils\gdal_calc.py build\lib.win-amd64-3.7\osgeo\utils\gdal_edit.py build\lib.win-amd64-3.7\osgeo\utils\gdal_fillnodata.py build\lib.win-amd64-3.7\osgeo\utils\gdal_merge.py build\lib.win-amd64-3.7\osgeo\utils\gdal_pansharpen.py build\lib.win-amd64-3.7\osgeo\utils\gdal_polygonize.py build\lib.win-amd64-3.7\osgeo\utils\gdal_proximity.py build\lib.win-amd64-3.7\osgeo\utils\gdal_retile.py build\lib.win-amd64-3.7\osgeo\utils\gdal_sieve.py build\lib.win-amd64-3.7\osgeo\utils\mkgraticule.py build\lib.win-amd64-3.7\osgeo\utils\ogrmerge.py build\lib.win-amd64-3.7\osgeo\utils\pct2rgb.py build\lib.win-amd64-3.7\osgeo\utils\rgb2pct.py build\lib.win-amd64-3.7\osgeo\utils\__init__.py
  Skipping optional fixer: ws_comma
  Fixing build\lib.win-amd64-3.7\osgeo\gdal.py build\lib.win-amd64-3.7\osgeo\gdalconst.py build\lib.win-amd64-3.7\osgeo\gdalnumeric.py build\lib.win-amd64-3.7\osgeo\gdal_array.py build\lib.win-amd64-3.7\osgeo\gnm.py build\lib.win-amd64-3.7\osgeo\ogr.py build\lib.win-amd64-3.7\osgeo\osr.py build\lib.win-amd64-3.7\osgeo\__init__.py build\lib.win-amd64-3.7\osgeo\utils\epsg_tr.py build\lib.win-amd64-3.7\osgeo\utils\esri2wkt.py build\lib.win-amd64-3.7\osgeo\utils\gcps2vec.py build\lib.win-amd64-3.7\osgeo\utils\gcps2wld.py build\lib.win-amd64-3.7\osgeo\utils\gdal2xyz.py build\lib.win-amd64-3.7\osgeo\utils\gdalchksum.py build\lib.win-amd64-3.7\osgeo\utils\gdalcompare.py build\lib.win-amd64-3.7\osgeo\utils\gdalident.py build\lib.win-amd64-3.7\osgeo\utils\gdalimport.py build\lib.win-amd64-3.7\osgeo\utils\gdalmove.py build\lib.win-amd64-3.7\osgeo\utils\gdal_auth.py build\lib.win-amd64-3.7\osgeo\utils\gdal_calc.py build\lib.win-amd64-3.7\osgeo\utils\gdal_edit.py build\lib.win-amd64-3.7\osgeo\utils\gdal_fillnodata.py build\lib.win-amd64-3.7\osgeo\utils\gdal_merge.py build\lib.win-amd64-3.7\osgeo\utils\gdal_pansharpen.py build\lib.win-amd64-3.7\osgeo\utils\gdal_polygonize.py build\lib.win-amd64-3.7\osgeo\utils\gdal_proximity.py build\lib.win-amd64-3.7\osgeo\utils\gdal_retile.py build\lib.win-amd64-3.7\osgeo\utils\gdal_sieve.py build\lib.win-amd64-3.7\osgeo\utils\mkgraticule.py build\lib.win-amd64-3.7\osgeo\utils\ogrmerge.py build\lib.win-amd64-3.7\osgeo\utils\pct2rgb.py build\lib.win-amd64-3.7\osgeo\utils\rgb2pct.py build\lib.win-amd64-3.7\osgeo\utils\__init__.py
  Skipping optional fixer: ws_comma
  running build_ext
  building 'osgeo._gdal' extension
  building 'osgeo._gdalconst' extension
  building 'osgeo._osr' extension
  building 'osgeo._ogr' extension
  building 'osgeo._gnm' extension
  building 'osgeo._gdal_array' extension
  error: Microsoft Visual C++ 14.0 is required. Get it with "Build Tools for Visual Studio": https://visualstudio.microsoft.com/downloads/
  ----------------------------------------
  ERROR: Failed building wheel for GDAL
  Running setup.py clean for GDAL
Failed to build GDAL
Installing collected packages: GDAL
    Running setup.py install for GDAL ... error
    ERROR: Command errored out with exit status 1:
     command: 'c:\users\{username}\appdata\local\programs\python\python37\python.exe' -u -c 'import 
sys, setuptools, tokenize; sys.argv[0] = '"'"'C:\\Users\\{username}\\AppData\\Local\\Temp\\pip-install-_i2yl6qm\\gdal\\setup.py'"'"'; __file__='"'"'C:\\Users\\{username}\\AppData\\Local\\Temp\\pip-install-_i2yl6qm\\gdal\\setup.py'"'"';f=getattr(tokenize, '"'"'open'"'"', open)(__file__);code=f.read().replace('"'"'\r\n'"'"', '"'"'\n'"'"');f.close();exec(compile(code, __file__, '"'"'exec'"'"'))' install --record 'C:\Users\{username}\AppData\Local\Temp\pip-record-o6x58230\install-record.txt' --single-version-externally-managed --compile --install-headers 'c:\users\{username}\appdata\local\programs\python\python37\Include\GDAL'
         cwd: C:\Users\{username}\AppData\Local\Temp\pip-install-_i2yl6qm\gdal\
    Complete output (54 lines):
    running install
    running build
    running build_py
    creating build
    creating build\lib.win-amd64-3.7
    creating build\lib.win-amd64-3.7\osgeo
    copying osgeo\gdal.py -> build\lib.win-amd64-3.7\osgeo
    copying osgeo\gdalconst.py -> build\lib.win-amd64-3.7\osgeo
    copying osgeo\gdalnumeric.py -> build\lib.win-amd64-3.7\osgeo
    copying osgeo\gdal_array.py -> build\lib.win-amd64-3.7\osgeo
    copying osgeo\gnm.py -> build\lib.win-amd64-3.7\osgeo
    copying osgeo\ogr.py -> build\lib.win-amd64-3.7\osgeo
    copying osgeo\osr.py -> build\lib.win-amd64-3.7\osgeo
    copying osgeo\__init__.py -> build\lib.win-amd64-3.7\osgeo
    creating build\lib.win-amd64-3.7\osgeo\utils
    copying osgeo\utils\epsg_tr.py -> build\lib.win-amd64-3.7\osgeo\utils
    copying osgeo\utils\esri2wkt.py -> build\lib.win-amd64-3.7\osgeo\utils
    copying osgeo\utils\gcps2vec.py -> build\lib.win-amd64-3.7\osgeo\utils
    copying osgeo\utils\gcps2wld.py -> build\lib.win-amd64-3.7\osgeo\utils
    copying osgeo\utils\gdal2xyz.py -> build\lib.win-amd64-3.7\osgeo\utils
    copying osgeo\utils\gdalchksum.py -> build\lib.win-amd64-3.7\osgeo\utils
    copying osgeo\utils\gdalcompare.py -> build\lib.win-amd64-3.7\osgeo\utils
    copying osgeo\utils\gdalident.py -> build\lib.win-amd64-3.7\osgeo\utils
    copying osgeo\utils\gdalimport.py -> build\lib.win-amd64-3.7\osgeo\utils
    copying osgeo\utils\gdalmove.py -> build\lib.win-amd64-3.7\osgeo\utils
    copying osgeo\utils\gdal_auth.py -> build\lib.win-amd64-3.7\osgeo\utils
    copying osgeo\utils\gdal_calc.py -> build\lib.win-amd64-3.7\osgeo\utils
    copying osgeo\utils\gdal_edit.py -> build\lib.win-amd64-3.7\osgeo\utils
    copying osgeo\utils\gdal_fillnodata.py -> build\lib.win-amd64-3.7\osgeo\utils
    copying osgeo\utils\gdal_merge.py -> build\lib.win-amd64-3.7\osgeo\utils
    copying osgeo\utils\gdal_pansharpen.py -> build\lib.win-amd64-3.7\osgeo\utils
    copying osgeo\utils\gdal_polygonize.py -> build\lib.win-amd64-3.7\osgeo\utils
    copying osgeo\utils\gdal_proximity.py -> build\lib.win-amd64-3.7\osgeo\utils
    copying osgeo\utils\gdal_retile.py -> build\lib.win-amd64-3.7\osgeo\utils
    copying osgeo\utils\gdal_sieve.py -> build\lib.win-amd64-3.7\osgeo\utils
    copying osgeo\utils\mkgraticule.py -> build\lib.win-amd64-3.7\osgeo\utils
    copying osgeo\utils\ogrmerge.py -> build\lib.win-amd64-3.7\osgeo\utils
    copying osgeo\utils\pct2rgb.py -> build\lib.win-amd64-3.7\osgeo\utils
    copying osgeo\utils\rgb2pct.py -> build\lib.win-amd64-3.7\osgeo\utils
    copying osgeo\utils\__init__.py -> build\lib.win-amd64-3.7\osgeo\utils
    c:\users\{username}\appdata\local\programs\python\python37\lib\site-packages\setuptools\lib2to3_ex.py:44: SetuptoolsDeprecationWarning: 2to3 support is deprecated. If the project still requires Python 2 support, please migrate to a single-codebase solution or employ an independent conversion process.
      SetuptoolsDeprecationWarning)
    Fixing build\lib.win-amd64-3.7\osgeo\gdal.py build\lib.win-amd64-3.7\osgeo\gdalconst.py build\lib.win-amd64-3.7\osgeo\gdalnumeric.py build\lib.win-amd64-3.7\osgeo\gdal_array.py build\lib.win-amd64-3.7\osgeo\gnm.py build\lib.win-amd64-3.7\osgeo\ogr.py build\lib.win-amd64-3.7\osgeo\osr.py build\lib.win-amd64-3.7\osgeo\__init__.py build\lib.win-amd64-3.7\osgeo\utils\epsg_tr.py build\lib.win-amd64-3.7\osgeo\utils\esri2wkt.py build\lib.win-amd64-3.7\osgeo\utils\gcps2vec.py build\lib.win-amd64-3.7\osgeo\utils\gcps2wld.py build\lib.win-amd64-3.7\osgeo\utils\gdal2xyz.py build\lib.win-amd64-3.7\osgeo\utils\gdalchksum.py build\lib.win-amd64-3.7\osgeo\utils\gdalcompare.py build\lib.win-amd64-3.7\osgeo\utils\gdalident.py build\lib.win-amd64-3.7\osgeo\utils\gdalimport.py build\lib.win-amd64-3.7\osgeo\utils\gdalmove.py build\lib.win-amd64-3.7\osgeo\utils\gdal_auth.py build\lib.win-amd64-3.7\osgeo\utils\gdal_calc.py build\lib.win-amd64-3.7\osgeo\utils\gdal_edit.py build\lib.win-amd64-3.7\osgeo\utils\gdal_fillnodata.py build\lib.win-amd64-3.7\osgeo\utils\gdal_merge.py build\lib.win-amd64-3.7\osgeo\utils\gdal_pansharpen.py build\lib.win-amd64-3.7\osgeo\utils\gdal_polygonize.py build\lib.win-amd64-3.7\osgeo\utils\gdal_proximity.py build\lib.win-amd64-3.7\osgeo\utils\gdal_retile.py build\lib.win-amd64-3.7\osgeo\utils\gdal_sieve.py build\lib.win-amd64-3.7\osgeo\utils\mkgraticule.py build\lib.win-amd64-3.7\osgeo\utils\ogrmerge.py build\lib.win-amd64-3.7\osgeo\utils\pct2rgb.py build\lib.win-amd64-3.7\osgeo\utils\rgb2pct.py build\lib.win-amd64-3.7\osgeo\utils\__init__.py
    Skipping optional fixer: ws_comma
    Fixing build\lib.win-amd64-3.7\osgeo\gdal.py build\lib.win-amd64-3.7\osgeo\gdalconst.py build\lib.win-amd64-3.7\osgeo\gdalnumeric.py build\lib.win-amd64-3.7\osgeo\gdal_array.py build\lib.win-amd64-3.7\osgeo\gnm.py build\lib.win-amd64-3.7\osgeo\ogr.py build\lib.win-amd64-3.7\osgeo\osr.py build\lib.win-amd64-3.7\osgeo\__init__.py build\lib.win-amd64-3.7\osgeo\utils\epsg_tr.py build\lib.win-amd64-3.7\osgeo\utils\esri2wkt.py build\lib.win-amd64-3.7\osgeo\utils\gcps2vec.py build\lib.win-amd64-3.7\osgeo\utils\gcps2wld.py build\lib.win-amd64-3.7\osgeo\utils\gdal2xyz.py build\lib.win-amd64-3.7\osgeo\utils\gdalchksum.py build\lib.win-amd64-3.7\osgeo\utils\gdalcompare.py build\lib.win-amd64-3.7\osgeo\utils\gdalident.py build\lib.win-amd64-3.7\osgeo\utils\gdalimport.py bui build\lib.win-amd64-3.7\osgeo\utils\pct2rgb.py build\lib.wimd64-3.7\osgeo\utils\gdal_auth.py buisgeo\utils\__init__.py                                      amd64-3.7\osgeo\utils\gdal_edit.py bu
    Skipping optional fixer: ws_comma                       ib.win-amd64-3.7\osgeo\utils\gdal_mer
    running build_ext                                        build\lib.win-amd64-3.7\osgeo\utils\
    building 'osgeo._gdal' extension                        proximity.py build\lib.win-amd64-3.7\
    building 'osgeo._osr' extension                         ls\gdal_sieve.py build\lib.win-amd64-
    building 'osgeo._ogr' extension                         \utils\ogrmerge.py build\lib.win-amd6
    building 'osgeo._gnm' extension                         tils\rgb2pct.py build\lib.win-amd64-3
    building 'osgeo._gdal_array' extension
    error: Microsoft Visual C++ 14.0 is required. Get it with "Build Tools for Visual Studio": https://visualstudio.microsoft.com/downloads/
    ----------------------------------------
ERROR: Command errored out with exit status 1: 'c:\users\{username}\appdata\local\programs\python\python37\python.exe' -u -c 'import sys, setuptools, tokenize; sys.argv[0] = '"'"'C:\\Users\\{username}\\AppData\\Local\\Temp\\pip-install-_i2yl6qm\\gdal\\setup.py'"'"'; __file__='"'"'C:\\Users\\{username}\\AppDah "Build Tools for Visual Studio": htta\\Local\\Temp\\pip-install-_i2yl6qm\\gdal\\setup.py'"'"';f=getattr(tokenize, '"'"'open'"'"', open)(__file__);code=f.read().replace('"'"'\r\n'"'"', '"'"'\n'"'"');f.close();exec(coam_z\appdata\local\programs\python\pympile(code, __file__, '"'"'exec'"'"'))' install --record 'C:sys.argv[0] = '"'"'C:\\Users\\{username}\Users\{username}\AppData\Local\Temp\pip-record-o6x58230\instal'"'"'; __file__='"'"'C:\\Users\\crhaml-record.txt' --single-version-externally-managed --compile py'"'"';f=getattr(tokenize, '"'"'open
--install-headers 'c:\users\{username}\appdata\local\programs\p '"'"'\n'"'"');f.close();exec(compileython\python37\Include\GDAL' Check the logs for full commands\{username}\AppData\Local\Temp\pip-reco output.                                                    managed --compile --install-headers '
PS C:\Users\{username}\1110_server (2)> pip install GDAL-3.1.4-ude\GDAL' Check the logs for full comProcessing c:\users\{username}\1110_server (2)\gdal-3.1.4-cp37-cp37m-win_amd64.whl
Installing collected packages: GDAL
Successfully installed GDAL-3.1.4
PS C:\Users\{username}\1110_server (2)> pip install fiona      
Collecting fiona
  Using cached Fiona-1.8.18.tar.gz (1.3 MB)
    ERROR: Command errored out with exit status 1:
     command: 'c:\users\{username}\appdata\local\programs\python\python37\python.exe' -c 'import sys, setuptools, tokenize; sys.argv[0] = '"'"'C:\\Users\\{username}\\AppData\\Local\\Temp\\pip-install-zsjvu_dy\\fiona\\setup.py'"'"'; __file__='"'"'C:\\Users\\{username}\\AppData\\Local\\Temp\\pip-install-zsjvu_dy\\fiona\\setup.py'"'"';f=getattr(tokenize, '"'"'open'"'"', open)(__file__);code=f.read().replace('"'"'\r\n'"'"', '"'"'\n'"'"');f.close();exec(compile(code, __file__, '"'"'exec'"'"'))' egg_info --egg-base 'C:\Users\{username}\AppData\Local\Temp\pip-pip-egg-info-jvah0ssa'
         cwd: C:\Users\{username}\AppData\Local\Temp\pip-install-zsjvu_dy\fiona\
    Complete output (1 lines):
    A GDAL API version must be specified. Provide a path to 
gdal-config using a GDAL_CONFIG environment variable or use 
a GDAL_VERSION environment variable.
    ----------------------------------------
ERROR: Command errored out with exit status 1: python setup.py egg_info Check the logs for full command output.
PS C:\Users\{username}\1110_server (2)> pip install Fiona-1.8.17-cp37-cp37m-win_amd64.whl
7-cp37m-win_amd64.whl
Collecting cligj>=0.5
  Downloading cligj-0.7.1-py3-none-any.whl (7.1 kB)
Requirement already satisfied: gdal~=3.1.2 in c:\users\{username}\appdata\local\programs\python\python37\lib\site-packages 
(from Fiona==1.8.17) (3.1.4)
Collecting munch
  Downloading munch-2.5.0-py2.py3-none-any.whl (10 kB)      
Collecting click-plugins>=1.0
  Downloading click_plugins-1.1.1-py2.py3-none-any.whl (7.5 
kB)
Requirement already satisfied: click>=4.0 in c:\users\{username}\appdata\local\programs\python\python37\lib\site-packages (from Fiona==1.8.17) (7.1.2)
Requirement already satisfied: six>=1.7 in c:\users\{username}\appdata\roaming\python\python37\site-packages (from Fiona==1.8.17) (1.15.0)
Collecting attrs>=17
  Downloading attrs-20.3.0-py2.py3-none-any.whl (49 kB)     
     |██████▌                         | 10 kB 639 kB/s eta 0     |█████████████                   | 20 kB 660 kB/s eta 0     |████████████████████            | 30 kB 495 kB/s eta 0     |██████████████████████████▌     | 40 kB 660 kB/s eta 0     |████████████████████████████████| 49 kB 627 kB/s      
Installing collected packages: cligj, munch, click-plugins, 
attrs, Fiona
Successfully installed Fiona-1.8.17 attrs-20.3.0 click-plugins-1.1.1 cligj-0.7.1 munch-2.5.0
PS C:\Users\{username}\1110_server (2)> pip install geopandas  
Collecting geopandas
  Using cached geopandas-0.8.1-py2.py3-none-any.whl (962 kB)
Requirement already satisfied: pandas>=0.23.0 in c:\users\{username}\appdata\roaming\python\python37\site-packages (from geopandas) (1.1.2)
Requirement already satisfied: shapely in c:\users\{username}\appdata\local\programs\python\python37\lib\site-packages (from geopandas) (1.7.1)
Requirement already satisfied: fiona in c:\users\{username}\appdata\local\programs\python\python37\lib\site-packages (from 
geopandas) (1.8.17)
Requirement already satisfied: pyproj>=2.2.0 in c:\users\{username}\appdata\local\programs\python\python37\lib\site-packages (from geopandas) (3.0.0.post1)
Requirement already satisfied: python-dateutil>=2.7.3 in c:\users\{username}\appdata\local\programs\python\python37\lib\site-packages (from pandas>=0.23.0->geopandas) (2.8.1)
Requirement already satisfied: pytz>=2017.2 in c:\users\{username}\appdata\roaming\python\python37\site-packages (from pandas>=0.23.0->geopandas) (2020.1)
Requirement already satisfied: numpy>=1.15.4 in c:\users\{username}\appdata\local\programs\python\python37\lib\site-packages (from pandas>=0.23.0->geopandas) (1.19.2)
Requirement already satisfied: attrs>=17 in c:\users\{username}\appdata\local\programs\python\python37\lib\site-packages (from fiona->geopandas) (20.3.0)
Requirement already satisfied: cligj>=0.5 in c:\users\{username}\appdata\local\programs\python\python37\lib\site-packages (from fiona->geopandas) (0.7.1)
Requirement already satisfied: six>=1.7 in c:\users\{username}\appdata\roaming\python\python37\site-packages (from fiona->geopandas) (1.15.0)
Requirement already satisfied: munch in c:\users\{username}\appdata\local\programs\python\python37\lib\site-packages (from fiona->geopandas) (2.5.0)
Requirement already satisfied: click>=4.0 in c:\users\{username}\appdata\local\programs\python\python37\lib\site-packages (from fiona->geopandas) (7.1.2)
Requirement already satisfied: gdal~=3.1.2 in c:\users\{username}\appdata\local\programs\python\python37\lib\site-packages (from fiona->geopandas) (3.1.4)
Requirement already satisfied: click-plugins>=1.0 in c:\users\{username}\appdata\local\programs\python\python37\lib\site-packages (from fiona->geopandas) (1.1.1)
Requirement already satisfied: certifi in c:\users\{username}\appdata\local\programs\python\python37\lib\site-packages (from pyproj>=2.2.0->geopandas) (2020.6.20)
Installing collected packages: geopandas
Successfully installed geopandas-0.8.1
```



참고 : https://codedragon.tistory.com/9556
