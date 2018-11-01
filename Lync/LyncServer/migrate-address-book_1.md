---
title: Migrar la libreta de direcciones
TOCTitle: Migrar la libreta de direcciones
ms:assetid: b6e000ce-8b2e-460c-8a8b-000254b9d778
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205198(v=OCS.15)
ms:contentKeyID: 48276451
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migrar la libreta de direcciones

 

_**Última modificación del tema:** 2012-10-02_

**Para migrar reglas de normalización personalizadas de la libreta de direcciones**

1.  Busque el archivo Company\_Phone\_Number\_Normalization\_Rules.txt en el directorio raíz de la carpeta compartida de la libreta de direcciones y cópielo al directorio raíz de la carpeta compartida de la libreta de direcciones de su grupo piloto de Lync Server 2013.
    

    > [!NOTE]
    > Las reglas de normalización de la libreta de direcciones de muestra se instalaron en el directorio de archivos de componentes web de ABS. La ruta es <STRONG>$installedDriveLetter:\Archivos de programa\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt</STRONG>. Este archivo se puede copiar y su nombre se puede cambiar a <STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> en el directorio raíz de la carpeta compartida de la libreta de direcciones. Por ejemplo, para la carpeta compartida <STRONG>$serverX</STRONG>, la ruta será similar a: <STRONG>\\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.



2.  Use un editor de texto (como el Bloc de notas) para abrir el archivo Company\_Phone\_Number\_Normalization\_Rules.txt.

3.  Determinados tipos de entradas no funcionarán correctamente en Lync Server 2013. Busque en el archivo los tipos de entradas que se describen en este paso, modifíquelos como sea necesario y guarde los cambios en la carpeta compartida de la libreta de direcciones de su grupo piloto.
    
    Las cadenas que contienen puntuación o espacios en blanco necesarios provocan errores en las reglas de normalización, ya que estos caracteres se quitan de la cadena que se incluye en las reglas de normalización. Si tiene cadenas que incluyen puntuación o espacios en blanco necesarios, deberá modificarlas. Por ejemplo, la siguiente cadena generará un error en la regla de normalización:
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    La siguiente cadena no provocará errores en la regla de normalización:
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

