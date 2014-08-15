# Templates

## Common template style

* <a name="template-style"></a>See example. <sup>[[link](#template-style)]</sup>
```HTML+PHP
# bad
<div>
    <? if ($last) : ?>
        <div class="last"></div>
    <? endif; ?>
</div>

# good
<div><?
    if ($last) :
        ?><div class="last"></div><?
    endif;
?></div>
```

* <a name="redundant-spaces"></a> Do not put space if it does not appear in all cases. <sup>[[link](#redundant-spaces)]</sup>
```HTML+PHP
# bad
<div <?
    if ($last) :
        ?>class="last"<?
    endif;
?>></div>

<div class="block <?
    if ($last) :
        ?>last<?
    endif;
?>"></div>

# good
<div<?
    if ($last) :
        ?> class="last"<?
    endif;
?>></div>

<div class="block<?
    if ($last) :
        ?> last<?
    endif;
?>"></div>

# still good
<div class="block <?
    if ($red) :
        ?>red<?
    else :
        ?>blue<?
    endif;
?>"></div>

<div class="block <?
    if ($red) :
        ?>red<?
    endif;
    if ($last) :
        ?>last<?
    endif;
?>"></div>
```

* <a name="first-block-indent"></a> Do not indent inside the first block. <sup>[[link](#first-block-indent)]</sup>
```HTML+PHP
# bad
<?php
    $items = array();
?><div></div>

# good
<?php
$items = array();
?><div></div>
```


* <a name="inline-control-structures"></a> Do not use control structures inline. <sup>[[link](#inline-control-structures)]</sup>
```HTML+PHP
# bad
<div<? if ($last) : ?> class="last"<? endif; ?>></div>

#good
<div<?
    if ($last) :
        ?> class="last"<?
    endif;
?>></div>
```

* <a name="html-comments"></a> Do not use html comments. <sup>[[link](#html-comments)]</sup>
```HTML+PHP
# bad
<!--<div><?= $title ?></div>-->
<div><?= $name ?></div><!-- name of page -->

# good
<? /* <div><?= $title ?></div> */ ?>

<div><?= $name ?></div><?#= name of page ?>
```

## PHP template style

* <a name="php-tag"></a> Use `<?php` on top of template, `<?` otherwise. <sup>[[link](#php-tag)]</sup>
```HTML+PHP
# bad
<div><?php
    $count = 0;
?></div>

# good
<?php
$count = 0;
?><div><?
    $totalCount = 13;
?></div>
```

* <a name="php-closing-tag"></a> Do not use `?>` at the end of file. <sup>[[link](#php-closing-tag)]</sup>
```HTML+PHP
# bad
<div class="clear"></div><?
$count = 0;
?>

# good
<div class="clear"></div><?
$count = 0;
```

* <a name="alternative-control-structures"></a> Use alternative syntax for control structures. <sup>[[link](#alternative-control-structures)]</sup>
```HTML+PHP
# bad
<div><?
    if ($hasLink) {
        ?><a href="<?= $link ?>"><?= $title ?></a><?
    }
?></div>

# good
<div><?
    if ($hasLink) :
        ?><a href="<?= $link ?>"><?= $title ?></a><?
    endif;
?></div>
```

* <a name="php-prinitng-variables"></a> Use `<?=` `?>` for printing variables inline, use `echo` otherwise. <sup>[[link](#php-prinitng-variables)]</sup>
```HTML+PHP
# bad
<div><? echo $title; ?></div>

<div>
    <?= $title ?>
</div>

# good
<div><?= $title ?></div>

<div><?
    echo $title;
?></div>
```

## Ruby template style

* <a name="ruby-closing-tag"></a> Do not put end of line before `%>` if it is last symbol. <sup>[[link](#ruby-closing-tag)]</sup>
```HTML+Ruby
# bad
<div></div><%
count = 0
%>

# good
<div></div><%
count = 0 %>
```

* <a name="ruby-prinitng-variables"></a> Use `<%=` `%>` for printing variables inline, use `concat` otherwise. <sup>[[link](#ruby-prinitng-variables)]</sup>
```HTML+Ruby
# bad
<div><% concat $title; %></div>

<div>
    <%= $title %>
</div>

# good
<div><%= $title %></div>

<div><%
    concat $title;
%></div>
```