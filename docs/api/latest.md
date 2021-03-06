# API Docs - v4.0.4-SNAPSHOT

## R

### eval *<a target="_blank" href="https://wso2.github.io/siddhi/documentation/siddhi-4.0/#stream-processor">(Stream Processor)</a>*

<p style="word-wrap: break-word">R script Stream processor. This extension runs the R script loaded from a file to each event and produces aggregated outputs based on the provided input variable parameters and expected output attributes.</p>

<span id="syntax" class="md-typeset" style="display: block; font-weight: bold;">Syntax</span>
```
r:eval(<STRING> script, <INT|LONG|FLOAT|DOUBLE|STRING|STRING> output.attributes, <INT|LONG|FLOAT|DOUBLE|STRING|STRING> input.attributes)
```

<span id="query-parameters" class="md-typeset" style="display: block; color: rgba(0, 0, 0, 0.54); font-size: 12.8px; font-weight: bold;">QUERY PARAMETERS</span>
<table>
    <tr>
        <th>Name</th>
        <th style="min-width: 20em">Description</th>
        <th>Default Value</th>
        <th>Possible Data Types</th>
        <th>Optional</th>
        <th>Dynamic</th>
    </tr>
    <tr>
        <td style="vertical-align: top">script</td>
        <td style="vertical-align: top; word-wrap: break-word">R script as a string produces aggregated outputs based on the provided input variable parameters and expected output attributes</td>
        <td style="vertical-align: top"></td>
        <td style="vertical-align: top">STRING</td>
        <td style="vertical-align: top">No</td>
        <td style="vertical-align: top">No</td>
    </tr>
    <tr>
        <td style="vertical-align: top">output.attributes</td>
        <td style="vertical-align: top; word-wrap: break-word">A set of output attributes separated by commas as string. Each attribute is denoted as &lt;name&gt;&lt;space&gt;&lt;type&gt;. e.g., 'output1 string, output2 long'</td>
        <td style="vertical-align: top"></td>
        <td style="vertical-align: top">INT<br>LONG<br>FLOAT<br>DOUBLE<br>STRING<br>STRING</td>
        <td style="vertical-align: top">No</td>
        <td style="vertical-align: top">No</td>
    </tr>
    <tr>
        <td style="vertical-align: top">input.attributes</td>
        <td style="vertical-align: top; word-wrap: break-word">A set of input attributes separated by commas after output attributes. e.g., 'att1, att2'</td>
        <td style="vertical-align: top"></td>
        <td style="vertical-align: top">INT<br>LONG<br>FLOAT<br>DOUBLE<br>STRING<br>STRING</td>
        <td style="vertical-align: top">No</td>
        <td style="vertical-align: top">No</td>
    </tr>
</table>
<span id="extra-return-attributes" class="md-typeset" style="display: block; font-weight: bold;">Extra Return Attributes</span>
<table>
    <tr>
        <th>Name</th>
        <th style="min-width: 20em">Description</th>
        <th>Possible Types</th>
    </tr>
    <tr>
        <td style="vertical-align: top">outputParameters</td>
        <td style="vertical-align: top; word-wrap: break-word">This runs the R script for each event and produces  aggregated outputs based on the provided input variable parameters and expected output attributes.</td>
        <td style="vertical-align: top">INT<br>LONG<br>FLOAT<br>DOUBLE<br>STRING<br>STRING</td>
    </tr>
</table>

<span id="examples" class="md-typeset" style="display: block; font-weight: bold;">Examples</span>
<span id="example-1" class="md-typeset" style="display: block; color: rgba(0, 0, 0, 0.54); font-size: 12.8px; font-weight: bold;">EXAMPLE 1</span>
```
@info(name = 'query1')
from weather#window.lengthBatch(2)#r:eval("c <- sum(time); m <- sum(temp); ", "c long, m double", time, temp) 
select * 
insert into dataOut;
```
<p style="word-wrap: break-word">TBD</p>

### evalSource *<a target="_blank" href="https://wso2.github.io/siddhi/documentation/siddhi-4.0/#stream-processor">(Stream Processor)</a>*

<p style="word-wrap: break-word">R source Stream processor. This extension the R script loaded from a file to each event and produces aggregated outputs based on the provided input variable parameters and expected output attributes.</p>

<span id="syntax" class="md-typeset" style="display: block; font-weight: bold;">Syntax</span>
```
r:evalSource(<STRING> file.path, <INT|LONG|FLOAT|DOUBLE|STRING|STRING> output.attributes, <INT|LONG|FLOAT|DOUBLE|STRING|STRING> input.attributes)
```

<span id="query-parameters" class="md-typeset" style="display: block; color: rgba(0, 0, 0, 0.54); font-size: 12.8px; font-weight: bold;">QUERY PARAMETERS</span>
<table>
    <tr>
        <th>Name</th>
        <th style="min-width: 20em">Description</th>
        <th>Default Value</th>
        <th>Possible Data Types</th>
        <th>Optional</th>
        <th>Dynamic</th>
    </tr>
    <tr>
        <td style="vertical-align: top">file.path</td>
        <td style="vertical-align: top; word-wrap: break-word">The file path of the R script where this script uses the input variable parameters and produces the expected output attributes.</td>
        <td style="vertical-align: top"></td>
        <td style="vertical-align: top">STRING</td>
        <td style="vertical-align: top">No</td>
        <td style="vertical-align: top">No</td>
    </tr>
    <tr>
        <td style="vertical-align: top">output.attributes</td>
        <td style="vertical-align: top; word-wrap: break-word">A set of output attributes separated by commas as string. Each attribute is denoted as &lt;name&gt;&lt;space&gt;&lt;type&gt;. e.g., 'output1 string, output2 long'</td>
        <td style="vertical-align: top"></td>
        <td style="vertical-align: top">INT<br>LONG<br>FLOAT<br>DOUBLE<br>STRING<br>STRING</td>
        <td style="vertical-align: top">No</td>
        <td style="vertical-align: top">No</td>
    </tr>
    <tr>
        <td style="vertical-align: top">input.attributes</td>
        <td style="vertical-align: top; word-wrap: break-word">A set of input attributes separated by commas after output attributes. e.g., 'att1, att2'</td>
        <td style="vertical-align: top"></td>
        <td style="vertical-align: top">INT<br>LONG<br>FLOAT<br>DOUBLE<br>STRING<br>STRING</td>
        <td style="vertical-align: top">No</td>
        <td style="vertical-align: top">No</td>
    </tr>
</table>
<span id="extra-return-attributes" class="md-typeset" style="display: block; font-weight: bold;">Extra Return Attributes</span>
<table>
    <tr>
        <th>Name</th>
        <th style="min-width: 20em">Description</th>
        <th>Possible Types</th>
    </tr>
    <tr>
        <td style="vertical-align: top">outputParameters</td>
        <td style="vertical-align: top; word-wrap: break-word">This runs the R script for each event and produces  aggregated outputs based on the provided input variable parameters and expected output attributes.</td>
        <td style="vertical-align: top">INT<br>LONG<br>FLOAT<br>DOUBLE<br>STRING<br>STRING</td>
    </tr>
</table>

<span id="examples" class="md-typeset" style="display: block; font-weight: bold;">Examples</span>
<span id="example-1" class="md-typeset" style="display: block; color: rgba(0, 0, 0, 0.54); font-size: 12.8px; font-weight: bold;">EXAMPLE 1</span>
```
@info(name = 'query1')
from weather#window.lengthBatch(2)#r:evalSource("src/test/resources/sample2.R", "m int, c float", time, temp)
select *
insert into dataOut;
```
<p style="word-wrap: break-word">This r source function takes in a r script file location and computes the output as defined in the file.</p>

