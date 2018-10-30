---
title: Configuración del almacén de contactos personales en equipos cliente
TOCTitle: Configuración del almacén de contactos personales en equipos cliente
ms:assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721922(v=OCS.15)
ms:contentKeyID: 49889798
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración del almacén de contactos personales en equipos cliente

 

_**Última modificación del tema:** 2016-12-08_

Para la integración de Microsoft Lync Server 2013 y Microsoft Exchange Server 2013, se recomienda configurar el almacén de contactos personales de todos los equipos clientes que ejecuten Microsoft Lync 2010. Concretamente, configure Lync para usar Exchange como almacén de contactos personal y, al mismo tiempo, garantizar que los usuarios no pueden cancelar esta decisión. Puede hacerlo creando y configurando un valor del Registro en cada equipo cliente.

Tenga en cuenta que no es obligatorio en los equipos que ejecutan Lync 2013.

Para configurar este valor en un solo equipo, siga este procedimiento:

1.  En el equipo cliente, haga clic en **Inicio** y en **Ejecutar**.

2.  En el cuadro de diálogo **Ejecutar**, escriba regedit y presione ENTRAR.

3.  En el Editor del Registro, expanda **HKEY\_LOCAL\_MACHINE**, **Software**, **Directivas**, **Microsoft** y, por último, **Communicator**.

4.  Haga clic con el botón secundario en **Communicator**, seleccione **Nuevo** y, a continuación, haga clic en **Valor DWORD (32 bits)**.

5.  Tras crear el nuevo valor, escriba **PersonalContactStoreOverride** y presione ENTRAR para cambiar el nombre del valor.

6.  Compruebe que el valor de PersonalContactStoreOverride es 0 y, a continuación, cierre el Editor del Registro.

Si necesita realizar este procedimiento en más de un equipo, cree un objeto Directiva de grupo personalizado. Para obtener información detallada, consulte la documentación sobre directivas de grupo en [http://go.microsoft.com/fwlink/?linkid=268543\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=268543%26clcid=0xc0a).

