---
title: Migrar libreta de direcciones
TOCTitle: Migrar libreta de direcciones
ms:assetid: ac7f0f39-4c6d-4702-8e25-93a73e3d800f
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205160(v=OCS.15)
ms:contentKeyID: 48276337
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migrar libreta de direcciones

 

_**Última modificación del tema:** 2012-10-09_

En general, la libreta de direcciones de Lync Server 2010 se migra con el resto de la topología. Ahora bien, es posible que deba realizar algunos pasos posteriores a la migración si personalizó los siguientes elementos en el entorno de Lync Server 2010:

  - Estableció la propiedad **PartitionbyOU** de WMI para agrupar entradas de la libreta de direcciones por unidad organizativa.

  - Personalizó las reglas de normalización de la libreta de direcciones.

  - Modificó el valor predeterminado del parámetro **UseNormalizationRules** a False.

**Entradas agrupadas de la libreta de direcciones**

Si estableció la propiedad **PartitionbyOU** de WMI en True para crear libretas de direcciones para cada unidad organizativa, deberá establecer el atributo **msRTCSIP-GroupingId** de Active Directory en los usuarios y contactos si desea seguir agrupando entradas de libretas de direcciones. Puede que le interese agrupar entradas para limitar el alcance de las búsquedas en las libretas de direcciones. Si desea usar el atributo **msRTCSIP-GroupingId** , escriba un script para rellenar el atributo y asigne el mismo valor a todos los usuarios que desea agrupar. Por ejemplo, asigne un único valor a todos los usuarios de una unidad organizativa.

**Reglas de normalización de la libreta de direcciones**

Si personalizó las reglas de normalización de la libreta de direcciones en el entorno de Lync Server 2010, deberá migrar las reglas personalizadas a su grupo piloto. Si no personalizó las reglas de normalización de la libreta de direcciones, no tendrá nada que migrar al servicio de libreta de direcciones (ABS). Las reglas de normalización predeterminadas para Lync Server 2013 son las mismas que las reglas predeterminadas para Lync Server 2010. Siga el procedimiento que se describe más adelante en esta sección para migrar reglas de normalización personalizadas.


> [!NOTE]
> Si su organización usa el control remoto de llamadas y personalizó las reglas de normalización de la libreta de direcciones, deberá llevar a cabo el procedimiento que se describe en este tema para poder usar el control remoto de llamadas. El procedimiento requiere pertenecer al grupo RTCUniversalServerAdmins o contar con derechos equivalentes.



**Definición de UseNormalizationRules en False**

Si establece el valor de **UseNormalizationRules** en False para que los usuarios puedan usar los números de teléfono como se definieron en Servicios de dominio de Active Directory sin que Lync Server 2013 aplique reglas de normalización, deberá establecer los parámetros **UseNormalizationRules** e **IgnoreGenericRules** en True. Siga el procedimiento que se describe más adelante en esta sección para establecer estos parámetros en True.

## Para migrar reglas de normalización personalizadas de la libreta de direcciones

1.  Busque el archivo Company\_Phone\_Number\_Normalization\_Rules.txt en el directorio raíz de la carpeta compartida de la libreta de direcciones y cópielo al directorio raíz de la carpeta compartida de la libreta de direcciones de su grupo piloto de Lync Server 2013.
    

    > [!NOTE]
    > Las reglas de normalización de la libreta de direcciones de muestra se instalaron en el directorio de archivos de componentes web de ABS. La ruta es <STRONG>$installedDriveLetter:\Archivos de programa\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt</STRONG>. Este archivo se puede copiar y su nombre se puede cambiar a <STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> en el directorio raíz de la carpeta compartida de la libreta de direcciones. Por ejemplo, para la carpeta compartida <STRONG>$serverX</STRONG>, la ruta será similar a: <STRONG>\\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.



2.  Use un editor de texto (como el Bloc de notas) para abrir el archivo Company\_Phone\_Number\_Normalization\_Rules.txt.

3.  Determinados tipos de entradas no funcionarán correctamente en Lync Server 2013. Busque en el archivo los tipos de entradas que se describen en este paso, modifíquelos como sea necesario y guarde los cambios en la carpeta compartida de la libreta de direcciones de su grupo piloto.
    
    Las cadenas que contienen puntuación o espacios en blanco necesarios provocan errores en las reglas de normalización, ya que estos caracteres se quitan de la cadena que se incluye en las reglas de normalización. Si tiene cadenas que incluyen puntuación o espacios en blanco necesarios, deberá modificarlas. Por ejemplo, la siguiente cadena generará un error en la regla de normalización:
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    La siguiente cadena no provocará errores en la regla de normalización:
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

## Para establecer UseNormalizationRules e IgnoreGenericRules en True

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Siga uno de estos pasos:
    
      - Si su implementación solamente incluye Lync Server 2013, ejecute el siguiente cmdlet en el nivel global para cambiar los valores de **UseNormalizationRules** e **IgnoreGenericRules** a True:
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - Si su implementación incluye una combinación de Lync Server 2013 y Lync Server 2010 u Office Communications Server 2007 R2, ejecute el siguiente cmdlet y asígnelo a cada grupo de servidores Lync Server 2013 de la topología:
        
            New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  Espere hasta que la replicación de Almacén de administración central se complete en todos los grupos de servidores.

4.  Modifique el archivo de reglas de normalización del teléfono, "Company\_Phone\_Number\_Normalization\_Rules.txt", de su implementación para borrar el contenido. El archivo se encuentra en el recurso compartido de archivos de cada grupo de servidores Lync Server 2013. Si no encuentra el archivo, cree un archivo vacío con el nombre "Company\_Phone\_Number\_Normalization\_Rules.txt".

5.  Espere varios minutos hasta que todos los Grupos de servidores front-end lean los nuevos archivos.

6.  Ejecute el siguiente cmdlet en cada grupo de servidores Lync Server 2013 de la implementación:
    
        Update-CsAddressBook

