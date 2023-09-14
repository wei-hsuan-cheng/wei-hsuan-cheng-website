Just code
=====

Key goals
-----

Options
-----
.. _hwcodeOptions:

Hi are you from the targetedlinks in homepage? 

Scratch
~~~~~

KidsRuby
~~~~~

Python
~~~~~

Here is some ``Python`` code for *GA* environment setup:

.. code-block:: python

    from clifford.g2c import *

    point = up(2 * e1 + e2)
    line = up(3 * e1 + 2 * e2) ^ up(3 * e1 - 2 * e2) ^ einf
    circle = up(e1) ^ up(-e1 + 2 * e2) ^ up(-e1 - 2 * e2)

    # point and line reflected in the circle

    point_refl = circle * point.gradeInvol() * ~circle
    line_refl = circle * line.gradeInvol() * ~circle

    # pyganja
    from pyganja import GanjaScene, draw
    import pyganja; pyganja.__version__

    # GanjaScene: build scenes out of geometric objects, with attached labels and RGB colors:

    sc = GanjaScene()
    sc.add_object(point, color=(255, 0, 0), label='point')
    sc.add_object(line, color=(0, 255, 0), label='line')
    sc.add_object(circle, color=(0, 0, 255), label='circle')

    sc_refl = GanjaScene()
    sc_refl.add_object(point_refl, color=(128, 0, 0), label='point_refl')
    sc_refl.add_object(line_refl, color=(0, 128, 0), label='line_refl')

    draw(sc, sig=layout.sig, scale=0.5)
    draw(sc + sc_refl, sig=layout.sig, scale=0.5) # A cool feature of GanjaScene is the ability to use "+" to draw both scenes together:

    # mpl_toolkits.clifford

    from matplotlib import pyplot as plt
    plt.ioff()  # we'll ask for plotting when we want it

    # if you're editing this locally, you'll get an interactive UI if you uncomment the following
    #
    #    %matplotlib notebook

    from mpl_toolkits.clifford import plot
    import mpl_toolkits.clifford; mpl_toolkits.clifford.__version__

    # standard matplotlib stuff - construct empty plots side-by-side, and set the scaling
    fig, (ax_before, ax_both) = plt.subplots(1, 2, sharex=True, sharey=True)
    ax_before.set(xlim=[-4, 4], ylim=[-4, 4], aspect='equal')
    ax_both.set(xlim=[-4, 4], ylim=[-4, 4], aspect='equal')

    # plot the objects before reflection on both plots
    for ax in (ax_before, ax_both):
        plot(ax, [point], color='tab:blue', label='point', marker='x', linestyle=' ')
        plot(ax, [line], color='tab:green', label='line')
        plot(ax, [circle], color='tab:red', label='circle')

    # plot the objects after reflection, with thicker lines
    plot(ax_both, [point_refl], color='tab:blue', label='point_refl',  marker='x', linestyle=' ', markeredgewidth=2)
    plot(ax_both, [line_refl], color='tab:green', label='line_refl', linewidth=2)

    fig.tight_layout()
    ax_both.legend()

    # show the figure
    fig

And here is some ``C#`` code:

.. code-block:: csharp

    private static string GetMessageFromException(Exception ex)
    {
        if (ex == null) return "";
        if (ex.InnerException != null)
        {
            return GetMessageFromException(ex.InnerException);
        }
        return ex.Message;
    }

Hopscotch
~~~~~

This is my cat, 髒髒包

.. image:: /images/my_cat.jpg

This is GA study group icon

.. image:: GA_study_group_icon.png
