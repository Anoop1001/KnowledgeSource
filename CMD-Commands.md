The below commands delete the folder "bin" and "obj" inside the entire folder structure recursively
FOR /F "tokens=*" %G IN ('DIR /B /AD /S bin') DO RMDIR /S /Q "%G"
FOR /F "tokens=*" %G IN ('DIR /B /AD /S obj') DO RMDIR /S /Q "%G"
