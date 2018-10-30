---
title: Uso de la herramienta de personalización de Office (OCT)
TOCTitle: Uso de la herramienta de personalización de Office (OCT)
ms:assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204748(v=OCS.15)
ms:contentKeyID: 48274711
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Uso de la herramienta de personalización de Office (OCT)

 

_**Última modificación del tema:** 2016-12-08_

La Herramienta de personalización de Office (OCT) forma parte del programa de instalación y es la herramienta recomendada para muchas de las personalizaciones. Al usar la OCT, puede personalizar su instalación de Office y guardar dichas personalizaciones en un archivo de configuración personalizada .msp y colocar el archivo en la carpeta Actualizaciones del punto de instalación de red. Al instalar Office, el programa de instalación busca un archivo de personalización del programa de instalación en la carpeta Actualizaciones y aplica dichas personalizaciones. La carpeta Actualizaciones solo puede utilizarse para implementar actualizaciones de software durante la instalación inicial de Office 2013.

La OCT forma parte de la instalación y está incluida en las versiones de licencia por volumen del producto. Puede ejecutar la OCT escribiendo `setup.exe /admin` en la línea de comandos de la raíz del punto de instalación de red que contenga los archivos de origen de Office 2013. Por ejemplo, utilice lo siguiente:

`\\server\share\Office15\setup.exe /admin`

Los administradores pueden utilizar la OCT para crear un archivo .msp de personalización de la instalación. Al igual que en la OCT de Microsoft Office 2010, los administradores pueden personalizar las siguientes áreas:

  - **Instalación** Se utiliza para especificar la ubicación predeterminada de la instalación en el cliente y el nombre de la organización predeterminado, los orígenes de instalación de red adicionales, la clave del producto, el contrato de licencia de usuario final, el nivel de presentación, las versiones anteriores de Office que se van a quitar, los programas personalizados que se van a ejecutar durante la instalación, la configuración de seguridad y las propiedades de instalación.

  - **Características** Se utiliza para establecer la configuración del usuario y para personalizar el modo en que se instalarán las características de Office. Los administradores pueden utilizar la OCT para especificar los valores iniciales predeterminados de la aplicación de Office para los usuarios. Los usuarios pueden modificar la mayoría de las opciones después de la instalación.

  - **Contenido adicional** Se utiliza para agregar o quitar archivos, para agregar o quitar entradas del Registro y para configurar accesos directos.

  - **Outlook** Se utiliza para personalizar el perfil de Outlook predeterminado de un usuario, especificar la configuración de Exchange, agregar cuentas, quitar cuentas y exportar configuraciones, así como para especificar grupos de envío o recepción.

Para obtener información sobre la OCT, vea [http://go.microsoft.com/fwlink/?linkid=267516\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=267516%26clcid=0xc0a).

