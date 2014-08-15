# Templates

- Common template style
-

- See example
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

- Do not put space if it does not appear in all cases
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

- Do not indent inside the first block
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


- Do not use control structures inline
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

- Do not use html comments
```HTML+PHP
# bad
<!--<div><?= $title ?></div>-->
<div><?= $name ?></div><!-- name of page -->

# good
<? /* <div><?= $title ?></div> */ ?>

<div><?= $name ?></div><?#= name of page ?>
```

- PHP template style
-

- Use `<?php` on top of template, `<?` otherwise
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

- Do not use `?>` at the end of file
```HTML+PHP
# bad
<div class="clear"></div><?
$count = 0;
?>

# good
<div class="clear"></div><?
$count = 0;
```

- Use alternative syntax for control structures
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

- Use `<?=` `?>` for printing variables inline, use `echo` otherwise
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

- Ruby template style
-

- Do not put end of line before `%>` if it is last symbol
```HTML+Ruby
# bad
<div></div><%
count = 0
%>

# good
<div></div><%
count = 0 %>
```

- Use `<%=` `%>` for printing variables inline, use `concat` otherwise
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