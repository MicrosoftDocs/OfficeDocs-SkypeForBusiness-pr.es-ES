---
title: Instalar paquete de compatibilidad con versiones anteriores de WMI
TOCTitle: Instalar paquete de compatibilidad con versiones anteriores de WMI
ms:assetid: 38797fbd-06a0-4008-b099-158e7b5d7703
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204816(v=OCS.15)
ms:contentKeyID: 48274930
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Instalar paquete de compatibilidad con versiones anteriores de WMI

 

_**Última modificación del tema:** 2012-10-02_

Si intenta ejecutar el asistente de combinación del asistente para combinaciones del Generador de topologías sin instalar el paquete de compatibilidad con versiones anteriores de WMI, verá el siguiente error:

![Mensaje de error de WMI](images/JJ204816.a007d2f2-fc85-430c-91eb-382b032469af(OCS.15).jpg "Mensaje de error de WMI")

Si intenta ejecutar el cmdlet **Merge-CsLegacytopology** sin instalar el paquete de compatibilidad con versiones anteriores de WMI, verá el siguiente error:

![Error de proveedor WMI de Windows PowerShell](images/JJ204816.c510824e-1807-4c7e-bb28-c6cfea2eac1d(OCS.15).jpg "Error de proveedor WMI de Windows PowerShell")

Para instalar el paquete de compatibilidad con versiones anteriores de WMI

1.  En el soporte de instalación, vaya a \\SETUP\\AMD64\\SETUP\\OCSWMIBC.MSI.

2.  Instale OCSWMIBC.MSI.
    
    > [!IMPORTANT]  
    > OCSWMIBC.msi debe instalarse en el equipo donde se ejecute el asistente de combinación del generador de topologías. Sin embargo, se recomienda instalar OCSWMIBC.msi en todos los servidores front-end de la topología.
    
    
    > [!IMPORTANT]  
    > OCSWMIBC.msi puede instalarse en cualquier equipo del dominio que tenga instalados los componentes básicos de Lync Server 2013 y la Shell de administración de Lync Server 2013 y que tenga acceso a la topología Office Communications Server 2007 R2 (proveedor WMI para Servicios de dominio de Active Directory (AD DS) y SQL Server).
    

