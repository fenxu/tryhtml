<?xml version="1.0" encoding="utf-8"?>
<html xmlns="http://www.w3.org/1999/xhtml">
  <head>
    <meta name="ROBOTS" content="NOINDEX, NOFOLLOW" />
    <meta http-equiv="Content-Location" content="" />
    <title>Comprobación de versiones en archivos redistribuibles</title>
    <link rel="parent" href="es-es/library/yw3yyscd(v=vs.80)" />
    <meta name="Microsoft.Help.TopicPublishDate" content="Tue, 28 Aug 2007 12:47:11 GMT" />
    <meta name="Microsoft.Help.TopicLocale" content="es-es" />
    <meta name="Microsoft.Help.TopicVersion" content="80" />
    <meta name="Microsoft.Help.Id" content="2f95d227-5deb-4f24-9c68-471e4b032b79" />
    <meta name="SelfBranded" content="false" />
    <meta name="Microsoft.Help.DisplayVersion" content="" />
    <meta name="Microsoft.Help.Locale" content="es-es" />
    <meta name="Title" content="Comprobación de versiones en archivos redistribuibles" />
    <meta name="Microsoft.Help.Category" content="DevLang:C++" />
    <meta name="Microsoft.Help.Keywords" content="archivos redistribuibles, comprobación de versiones" />
    <meta name="Description" content="Es importante instalar sólo la versión más reciente de un archivo. En casi todas las ocasiones, se desea instalar una versión más moderna de un archivo DLL o de un componente sobre una versión más antigua, y no al contrario. Los archivos DLL del sist . . ." />
    <meta name="Microsoft.Help.TocParentTopicVersion" content="80" />
    <meta name="Microsoft.Help.TocParent" content="37f1691e-d67c-41e4-926e-528a237a9bac" />
    <meta name="Microsoft.Help.TocRoot" content="ms310241 (en-us;MSDN.10)" />
    <meta name="Microsoft.Help.TocOrder" content="9" />
    <link type="text/css" rel="Stylesheet" href="C:\css\branding1.css" />
  </head>
  <body class="primary-mtps-offline-document">
    <div class="topic" xmlns:mtps="http://msdn2.microsoft.com/mtps" xmlns="http://www.w3.org/1999/xhtml">
      <div class="majorTitle" xmlns:asp="http://msdn2.microsoft.com/asp">Visual C++<!----></div>
      <div class="title" xmlns:asp="http://msdn2.microsoft.com/asp">Comprobación de versiones en archivos redistribuibles<!----></div>
      <!--Content type: DocStudio. Transform: devdiv2mtps.xslt.-->
      <div id="mainSection"> <div id="mainBody">  <p /> <p>Es importante instalar sólo la versión más reciente de un archivo. En casi todas las ocasiones, se desea instalar una versión más moderna de un archivo DLL o de un componente sobre una versión más antigua, y no al contrario. Los archivos DLL del sistema, como Kernel32.dll, User32.dll, Ole32.dll y ShDocVW.dll, no se deben redistribuir. Si se necesita redistribuir algún archivo, no olvide leer los contratos de licencia correspondientes y asegurarse de que los archivos pueden redistribuirse según las diferentes versiones del sistema operativo y la ubicación de instalación. Normalmente, la comprobación de versiones corresponde al programa de instalación.</p> <p>Si crea un programa de instalación propio, debe comprobar manualmente la información de la versión al instalar los archivos redistribuibles. Este tema incluye un programa de ejemplo que comprueba los números de versión, o si falta el número de versión de un archivo, las marcas de fecha y hora.</p> <h1 class="heading">Ejemplo</h1><div id="sectionSection0" class="seeAlsoNoToggleSection">  <div class="subSection"> <p>En el ejemplo siguiente se muestra un método para comprobar entre dos bibliotecas dinámicas o aplicaciones ejecutables.</p> </div> <div class="subSection"> <div class="CodeSnippetLanguage" xmlns=""><div class="codeSnippetContainerCodeContainer"><div class="CodeSnippetToolBarText" style="valign: top"></div><div id="CodeSnippetContainerCode_0" class="CodeSnippetContainerCode"><div style="color:Black;"><pre>
// checkversion.cpp
// compile with: /link version.lib

#include &lt;windows.h&gt;
#include &lt;stdio.h&gt;

void EmitErrorMsg (HRESULT hr);
HRESULT GetFileVersion (char *filename, VS_FIXEDFILEINFO *vsf);
HRESULT GetFileDate (char *filename, FILETIME *pft);
HRESULT LastError();
int WhichIsNewer (char *fname1, char *fname2);

void printtime (FILETIME *t)
{
    FILETIME lft;
    FILETIME *ft = &amp;lft;
    FileTimeToLocalFileTime(t,ft);
    printf_s("%08x %08x",ft-&gt;dwHighDateTime,ft-&gt;dwLowDateTime); 
    {
        SYSTEMTIME stCreate;
        BOOL bret = FileTimeToSystemTime(ft,&amp;stCreate);
        printf_s("    %02d/%02d/%d  %02d:%02d:%02d\n",
                        stCreate.wMonth, stCreate.wDay, stCreate.wYear,
                        stCreate.wHour, stCreate.wMinute,
                        stCreate.wSecond);
    }
}

int main(int argc, char* argv[]) 
{
    printf_s("usage: checkversion file1 file2\n"
             "\tReports which file is newer, first by checking "
             "the file version in "
             "\tthe version resource, then by checking the date\n\n" );

    if (argc != 3) 
        return 1;

    int newer = WhichIsNewer(argv[1],argv[2]);
    switch(newer) 
    {
        case 1:
        case 2: 
            printf_s("%s is newer\n",argv[newer]); 
        break;
        case 3: 
            printf_s("they are the same version\n"); 
        break;
        case 0:
        default: 
            printf_s("there was an error\n"); 
        break;
    }

    return !newer;
}

int WhichIsNewer (char *fname1, char *fname2) 
{
    // 1 if argv[1] is newer
    // 2 if argv[2] is newer
    // 3 if they are the same version
    // 0 if there is an error

    int ndxNewerFile;
    HRESULT ret;
    VS_FIXEDFILEINFO vsf1,vsf2;

    if ( SUCCEEDED((ret=GetFileVersion(fname1,&amp;vsf1))) &amp;&amp;
         SUCCEEDED((ret=GetFileVersion(fname2,&amp;vsf2)))) 
    {
        // both files have a file version resource
        // compare by file version resource
        if (vsf1.dwFileVersionMS &gt; vsf2.dwFileVersionMS) 
        {
            ndxNewerFile = 1;
        }
        else 
            if (vsf1.dwFileVersionMS &lt; vsf2.dwFileVersionMS) 
            {
                ndxNewerFile = 2;
            }
            else {   
              // if (vsf1.dwFileVersionMS == vsf2.dwFileVersionMS)
              if (vsf1.dwFileVersionLS &gt; vsf2.dwFileVersionLS) {
                   ndxNewerFile = 1;
              }
              else 
                  if (vsf1.dwFileVersionLS &lt; vsf2.dwFileVersionLS) {
                      ndxNewerFile = 2;
              }
            else 
            {   
                // if (vsf1.dwFileVersionLS == vsf2.dwFileVersionLS)
                ndxNewerFile = 3;
            }
        }
    }
    else 
    {
        // compare by date
        FILETIME ft1,ft2;
        if (SUCCEEDED((ret=GetFileDate(fname1,&amp;ft1))) &amp;&amp;
            SUCCEEDED((ret=GetFileDate(fname2,&amp;ft2))))
        {
            LONG x = CompareFileTime(&amp;ft1,&amp;ft2);
            if (x == -1) 
                ndxNewerFile = 2;
            else 
                if (x == 0) 
                   ndxNewerFile = 3;
                else 
                   if (x == 1) 
                       ndxNewerFile = 1;
                   else 
                   {
                       EmitErrorMsg(E_FAIL);
                       return 0;
                   }
        }
        else 
        {
            EmitErrorMsg(ret);
            return 0;
        }
    }
    return ndxNewerFile;
}

HRESULT GetFileDate (char *filename, FILETIME *pft) 
{
    // we are interested only in the create time
    // this is the equiv of "modified time" in the 
    // Windows Explorer properties dialog
    FILETIME ct,lat;
    HANDLE hFile = CreateFile(filename, GENERIC_READ,FILE_SHARE_READ |
                         FILE_SHARE_WRITE,0,OPEN_EXISTING,0,0);
    if (hFile == INVALID_HANDLE_VALUE) 
        return LastError();
    BOOL bret = GetFileTime(hFile,&amp;ct,&amp;lat,pft);
    if (bret == 0) 
        return LastError();
    return S_OK;
}

// This function gets the file version info structure
HRESULT GetFileVersion (char *filename, VS_FIXEDFILEINFO *pvsf) 
{
    DWORD dwHandle;
    DWORD cchver = GetFileVersionInfoSize(filename,&amp;dwHandle);
    if (cchver == 0) 
        return LastError();
    char* pver = new char[cchver];
    BOOL bret = GetFileVersionInfo(filename,dwHandle,cchver,pver);
    if (!bret) 
        return LastError();
    UINT uLen;
    void *pbuf;
    bret = VerQueryValue(pver,"\\",&amp;pbuf,&amp;uLen);
    if (!bret) 
        return LastError();
    memcpy(pvsf,pbuf,sizeof(VS_FIXEDFILEINFO));
    delete[] pver;
    return S_OK;
}

HRESULT LastError () 
{
    HRESULT hr = HRESULT_FROM_WIN32(GetLastError());
    if (SUCCEEDED(hr)) 
        return E_FAIL;
    return hr;
}

// This little function emits an error message 
// based on WIN32 error messages
void EmitErrorMsg (HRESULT hr) 
{
    char szMsg[1024];
    FormatMessage( 
        FORMAT_MESSAGE_FROM_SYSTEM, 
        NULL,
        hr,
        MAKELANGID(LANG_NEUTRAL, SUBLANG_DEFAULT),
        szMsg,
        1024,
        NULL 
    );

    printf_s("%s\n",szMsg);
}
</pre></div></div></div></div> </div> </div><h1 class="heading"><span id="seeAlsoNoToggle">Vea también</span></h1><div id="seeAlsoSection" class="seeAlsoNoToggleSection"><h4 class="subHeading">Otros recursos</h4><span class="linkTerms"><a class="mtps-external-link" href="../zebw5zk9_es-es_vs.80/zebw5zk9.html">Implementación (C++)</a></span><br /><br /></div></div>  </div>
    </div>
  </body>
</html>