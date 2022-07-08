<!DOCTYPE html>

<html lang="en">
<head>
    <meta charset="utf-8" />
    <title>Zebra</title>
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />   <!-- needed because of:  http://stackoverflow.com/questions/13284083/ie10-renders-in-ie7-mode-how-to-force-standards-mode -->
    <!-- <link rel="stylesheet" type="text/css" href="http://yui.yahooapis.com/3.18.1/build/cssreset/cssreset-min.css">  http://yuilibrary.com/yui/docs/cssreset/  could be good idea to use this -->
    <link rel="stylesheet" href="zebra.css" type="text/css" />
    <script src="jquery.min.js"></script>
    <!-- <script src="jquery-3.1.0.slim.min.js"></script> -->
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.12.4/jquery.min.js"></script>
    <script src="parse.js"></script>
    <script src="table.js"></script>
    <script src="setup.js"></script>
    <script src="zebra.js"></script>

    <!-- because by default size of text in Chrome is lower than in other browsers (mainly Firefox), to achieve similiar look across all this hack is needed -->
    <script>
        if(navigator.userAgent.indexOf("Chrome") != -1 )
        {
             var fontsize = "<style>body{font-size: 125%;}</style>";
        }
        else if(navigator.userAgent.indexOf("Opera") != -1 )
        {
             var fontsize = "<style>body{font-size: 100%;}</style>";
        }
        else if(navigator.userAgent.indexOf("Firefox") != -1 )
        {
             var fontsize = "<style>body{font-size: 100%;}</style>";
        }
        else if((navigator.userAgent.indexOf("MSIE") != -1 ) || (!!document.documentMode == true )) //IF IE > 10
        {
             var fontsize = "<style>body {font-size: 100%;}</style>";
        }
        else
        {
             var fontsize = "<style>body {font-size: 100%;}</style>";
        }
        document.writeln(fontsize);
    </script>

</head>

<body>
    <h1 id="h1a" style="margin-left:60px; font-size:64px ; color:darkslategrey; margin-top: 15px; margin-bottom: 10px;">
        <img src="zebra.png" style="width:64px; height:64px" />
        Zebra 1.03
    </h1>

    <h2 style="margin-left:60px;  color:darkslategrey">GEN regioning visualizer</h2>
    <table id="content" align="center" style="align-content:center;align-items:center; align-self:center">
        <tr style="align-content:center; align-items:center; align-self:center">
            <td>
                <form style="align-content:center; align-items:center; align-self:center">
                    <br /><br />
                    <textarea id="textA" rows="15" style="width: 80%; font-family:Consolas,Courier New, Courier, monospace; font-size: 16px;"></textarea><br /><br />
                    <input type="button" id="button2" value="Visualise" />
                    <input type="button" id="button3" value="Clean" />
                    <input type="button" id="button4" value="Info List" />
                    <input type="button" id="button5" value="Help" />
                    <span>                            </span>
                    <select id="platforms" class="demo">
                        <option value='not-selected' selected>Choose platform (for send decoder): </option>
                        <option value='IVB'>IVB</option>
                        <option value='HSW'>HSW</option>
                        <option value='BDW'>BDW</option>
                        <option value='SKL'>SKL</option>
                        <option value='BXT'>BXT</option>
                        <option value='CHV'>CHV</option>
                    </select>
                    <select id="granularity" class="demo">
                        <option selected value='1'>Table granularity (default: bytes) </option>
                        <option value='1'>bytes</option>
                        <option value='2'>words</option>
                        <option value='4'>double words</option>
                        <option value='8'>quad words</option>
                        <option value='16'>octo words</option>
                    </select>
                    <br /><br /><br /><br /><br />
                </form>
            </td>
        </tr>
    </table>

    <table align="center" id="TableTable" width="90%" height="fixed" >
        <br />
        <tr>
            <td></td>
            <td></td>
        </tr>
    </table>

    
</body>
</html>
