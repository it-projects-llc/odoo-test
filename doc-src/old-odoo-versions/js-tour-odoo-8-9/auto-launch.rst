================================
 Auto Launch after installation
================================

To run tour after module installation do next steps.

    * Create *ToDo*
    * Create *Action*


ToDo is some queued web actions that may call *Action* like this::

    <record id="base.open_menu" model="ir.actions.todo">
        <field name="action_id" ref="action_website_tutorial"/>
        <field name="state">open</field>
    </record>

Action is like this::

    <record id="res_partner_mails_count_tutorial" model="ir.actions.act_url">
        <field name="name">res_partner_mails_count Tutorial</field>
        <field name="url">/web#id=3&amp;model=res.partner&amp;/#tutorial_extra.mails_count_tour=true</field>
        <field name="target">self</field>
    </record>

Here tutorial_extra.**mails_count_tour** is tour id.

Use eval to compute some python code if needed::

    <field name="url" eval="'/web?debug=1&amp;res_partner_mails_count=tutorial#id='+str(ref('base.partner_root'))+'&amp;view_type=form&amp;model=res.partner&amp;/#tutorial_extra.mails_count_tour=true'"/>

